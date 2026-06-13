# Bài 2: OWASP Top 10 for LLM Applications — Hiểu Rõ Từng Lỗ Hổng

## OWASP Top 10 for LLMs (2025 Edition)

| # | Vulnerability | Mô tả |
|---|---|---|
| 1 | **Prompt Injection** | Attacker thao túng input để LLM bỏ qua instructions gốc |
| 2 | **Insecure Output Handling** | Output từ LLM không được validate trước khi sử dụng |
| 3 | **Training Data Poisoning** | Data huấn luyện bị nhiễm độc |
| 4 | **Model Denial of Service** | Khai thác resource-intensive queries |
| 5 | **Supply Chain Vulnerabilities** | Model/component từ nguồn không tin cậy |
| 6 | **Sensitive Information Disclosure** | LLM tiết lộ dữ liệu nhạy cảm |
| 7 | **Insecure Plugin Design** | Plugin/tool có quyền quá rộng |
| 8 | **Excessive Agency** | Agent có quá nhiều quyền hành động |
| 9 | **Overreliance** | Tin tưởng output AI mà không verify |
| 10 | **Model Theft** | Trích xuất model weights/parameters |

## Frameworks liên quan

- **OWASP AI Testing Guide** — Framework thống nhất cho trustworthiness testing
- **OWASP LLMSVS** (LLM Security Verification Standard) — Tiêu chuẩn verification cho LLM systems
- **OWASP AI Exchange** — 200+ trang practical advice về AI security & privacy
- **Cloud Security Alliance** — Defense Playbook cho từng vulnerability

## Practical Defense per Vulnerability

### Prompt Injection

```python
# Multi-layer defense
def process_input(user_input, system_prompt):
    # Layer 1: Input sanitization
    sanitized = sanitize_input(user_input)
    
    # Layer 2: Delimiter-based separation
    full_prompt = f"""<|system|>{system_prompt}<|end|>
    <|user|>{sanitized}<|end|>"""
    
    # Layer 3: Output validation
    response = llm.generate(full_prompt)
    return validate_output(response, allowed_actions)
```

### Insecure Output Handling

```python
# Never trust LLM output directly
def safe_execute(llm_output):
    # Treat as untrusted user input
    parsed = json.loads(llm_output)  # structured output only
    validated = schema.validate(parsed)  # schema validation
    return execute_with_sandbox(validated)  # sandboxed execution
```

## References

- [OWASP Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OWASP AI Testing Guide](https://owasp.org/www-project-ai-testing-guide/)
- [OWASP AI Exchange](https://owasp.org/www-project-ai-security-and-privacy-guide/)
- [OWASP LLMSVS](https://owasp.org/www-project-llm-verification-standard/)
- [Cloud Security Alliance: Defense Playbook](https://cloudsecurityalliance.org/blog/2025/05/09/the-owasp-top-10-for-llms-csa-s-strategic-defense-playbook)
