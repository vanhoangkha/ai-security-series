# Bài 9: Deepfake & AI-Powered Social Engineering — Threat Mới

## Scale of the Problem (2026)

- **40%** BEC attacks dùng AI-generated deepfake (voice/video/text) — from <5% in 2023
- **53%** organizations đã bị impact bởi AI impersonation schemes
- Voice cloning từ **3 seconds of audio** với giá **dưới $20**
- **15 phút** để build complete attack dossier + deepfake

## Notable Attacks

### Hong Kong Finance Worker
- Video call với "multiple company executives" — tất cả là AI-synthesized
- Faces tạo từ publicly available video
- **15 wire transfers** to 5 accounts trước khi detect

### CEO Voice Fraud
- AI-generated voice giả CEO gọi cho subsidiary CEO
- Instruction: wire €220,000 to Hungarian supplier
- Wire đã thực hiện. Voice hoàn toàn AI-generated.

### Microsoft Teams + Voice Cloning
- Attacker tạo external Teams account
- Pose as IT helpdesk + AI voice cloning
- Target identified via LinkedIn/company directory

## Tại sao Traditional Defenses Fail?

- Deepfake attack surface nằm **ngoài** coverage của existing security stack
- Economics thay đổi: impersonation giờ cực rẻ
- AI phishing **outperform human red teams** entirely

## Defense Recommendations

1. **Out-of-band verification** — Separate channel cho financial/sensitive requests
2. **Code words/phrases** — Pre-agreed verification cho executives
3. **AI detection tools** — Arms race, không reliable 100%
4. **Process controls** — Dual approval cho wire transfers
5. **Awareness training** — Specifically cho AI-generated content
6. **Liveness detection** — Cho video calls quan trọng

## References

- [DigitalApplied: AI Deepfake Attacks Surge 40%](https://www.digitalapplied.com/blog/ai-deepfake-attacks-surge-40-percent-email-compromise)
- [BeyondScale: Deepfake Fraud Defense Guide](https://beyondscale.tech/blog/deepfake-fraud-enterprise-defense-guide)
- [ThreatLocker: Vishing & AI Voice Cloning](https://www.threatlocker.com/blog/ai-voice-cloning-and-vishing-attacks-what-every-business-must-know)
- [Illumio: Deepfaked in 15 Minutes](https://www.illumio.com/blog/i-got-deepfaked-in-15-minutes-heres-what-ai-powered-social-engineering-looks-like)
- [IANS Research: AI Impersonation New Playbook](https://www.iansresearch.com/resources/all-blogs/post/security-blog/2026/06/12/seeing-isn-t-believing--ai-impersonation-forces-a-new-security-playbook)
