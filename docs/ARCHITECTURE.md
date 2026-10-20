
---

## 5. `docs/ARCHITECTURE.md`

Dosya yolu: `docs/ARCHITECTURE.md`

Bu belge, Gemini’nin proje büyürken her şeyi tek dosyaya yığmasını veya gereksiz katmanlar oluşturmasını engeller.

```markdown
# Architecture — Luma Translate

## 1. Architecture goals

The architecture must support:

- Native Android screen capture
- On-device OCR
- A floating translation control
- A replaceable translation provider
- A polished, responsive user interface
- Minimal collection and retention of user data
- Automated tests and physical-device verification

The architecture must remain small until real product requirements justify
additional complexity.

## 2. System overview

```text
Android device
    |
    | User grants screen-capture consent
    v
MediaProjection capture
    |
    v
Local image processing
    |
    v
On-device OCR
    |
    | Recognized text only
    | + source/target language settings
    v
Luma backend over HTTPS
    |
    v
Request validation and rate limiting
    |
    v
Translation service interface
    |
    v
Configured translation provider
    |
    v
Validated translation response
    |
    v
Android translation result UI
