# Font Transfer Between Letters Using Pix2Pix

This project explores **font transfer between letters** using a Conditional GAN (pix2pix) architecture. The main motivation is that many fonts are only available for English characters, while Turkish uses the same alphabet with a few additional letters. This project attempts to transfer fonts from available letters to missing Turkish characters.

---

## 🎯 Project Motivation

Some fonts do not support Turkish-specific characters (e.g., Ç, Ğ, İ, Ş, Ö, Ü), even though Turkish largely shares the Latin alphabet with English. Instead of manually designing missing glyphs, this project uses a deep learning approach to **transfer font style from one letter to another**.

---

## 🧠 Approach

- A **pix2pix (Conditional GAN)** model is trained on paired letter images.
- A custom dataset is used, where:
  - Input: Letter **C**
  - Target: Letter **Ç**
- The model learns to translate the font style from one letter to the corresponding Turkish letter.
- The approach works best for **non-artistic / regular fonts**, while highly decorative fonts remain challenging.

---

## 🏗️ Model Architecture

- **Generator:** U-Net based architecture with skip connections.
- **Discriminator:** PatchGAN that classifies local image patches as real or fake.
- **Loss Function:**Total Generator Loss = GAN Loss + λ * L1 Loss where λ = 100.

---

## ⚙️ Training Details

- Framework: TensorFlow 2.15
- Environment: Google Colab
- Optimizer: Adam (lr = 0.0002, β1 = 0.5, β2 = 0.999)
- Batch size: 1
- Training steps: 40,000

---

## 📌 Results Summary

- Font transfer was **successful for regular fonts**.
- Performance decreases for **artistic or highly stylized fonts**.
- The model demonstrates the feasibility of generating missing glyphs using paired image translation.

---

## 📎 References

This project is based on the following works:

- **Isola et al., 2017** — *Image-to-Image Translation with Conditional Adversarial Networks*  
https://arxiv.org/abs/1611.07004

- TensorFlow Pix2Pix Tutorial  
https://www.tensorflow.org/tutorials/generative/pix2pix

---

## 👨‍💻 Developer

**Sadri Alp Güldür**  
[www.linkedin.com/in/sadri-alp-guldur]

---

## 📄 License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.

Feel free to fork, contribute, or open issues!