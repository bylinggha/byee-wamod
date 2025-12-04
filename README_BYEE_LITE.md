# Byee-WAMod

Fork dari [bail-lite](https://github.com/Lord-Samuel/Bail-lite) dengan custom messages.js support untuk interactiveButtons.

## 🎯 Perubahan dari Bail-Lite

### ✅ Custom Messages.js
- **Support InteractiveButtons** dengan `cta_url` button
- **Support Header** untuk image, video, document, location, product
- **Support Media Attachment** handling yang lebih baik
- **+103 baris kode** untuk interactive message support

### 📋 Fitur yang Ditambahkan

1. **InteractiveButtons Support**
   - Support untuk button dengan URL (`cta_url`)
   - Support untuk `NativeFlowMessage`
   - Support untuk text, image, video, document, location, product dengan interactiveButtons

2. **Header Support**
   - ImageMessage di header
   - VideoMessage di header
   - DocumentMessage di header
   - LocationMessage di header
   - ProductMessage di header
   - Title & Subtitle support

3. **Media Attachment Handling**
   - Proper `hasMediaAttachment` flag
   - Media di-copy ke header untuk interactive message

## 📦 Install

```bash
npm install github:YOUR_USERNAME/byee-wamod
# atau
npm install git+https://github.com/YOUR_USERNAME/byee-wamod.git
```

## 🚀 Usage

Sama seperti bail-lite, tapi dengan support interactiveButtons yang lebih lengkap:

```javascript
import makeWASocket from 'byee-wamod'

const sock = makeWASocket({
    auth: state,
    printQRInTerminal: true
})

// Send interactive message with image + button
await sock.sendMessage(jid, {
    image: { url: 'https://example.com/image.jpg' },
    caption: 'Body text',
    title: 'Title',
    subtitle: 'Subtitle',
    footer: 'Footer',
    interactiveButtons: [
        {
            name: 'cta_url',
            buttonParamsJson: JSON.stringify({
                display_text: 'Click Me!',
                url: 'https://example.com',
                merchant_url: 'https://example.com'
            })
        }
    ]
})
```

## 📝 License

MIT License - See LICENSE file for details.

## 🙏 Credits

- Original: [bail-lite](https://github.com/Lord-Samuel/Bail-lite) by Lord-Samuel
- Based on: [Baileys](https://github.com/WhiskeySockets/Baileys)

## ⚠️ Important

**JANGAN UPDATE messages.js tanpa backup!** File ini sudah dimodifikasi dengan custom code.

