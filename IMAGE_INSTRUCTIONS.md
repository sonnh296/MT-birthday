# Image Instructions for Birthday App

You need to add 3 more images to the `/public` folder to complete the app:

## Required Images:

1. **em_be.jpg** - An image representing a baby (for page 1)

   - This should represent "23 năm trước, có một em bé ra đời..."
   - You can use a baby photo or any cute baby image

2. **xinh_dep.jpg** - An image representing growing up/beauty (for page 2)

   - This should represent "Cô ấy lớn lên, dần dần, dần dần"
   - Could be a photo of Minh Thu when she was younger, or a beautiful/elegant image

3. **cow_and_human.jpg** - An image of a cow and human together (for page 3)
   - This should represent "1 người 1 bò" (one person, one cow)
   - Could be a funny photo of you two together, or a creative cow+human image

## How to Add Images:

1. Save your images with these exact names (or update the names in App.vue)
2. Place them in the `/public` folder
3. Supported formats: .jpg, .jpeg, .png

## Alternative:

If you don't have these images yet, you can:

- Use the existing images (MinhThu.jpeg, cho.png, meo1.png, etc.) as placeholders
- Update the image paths in App.vue lines 14-16 to use existing images

For example, in App.vue, change:

```javascript
const pages = [
  {
    image: "/meo1.png", // Use existing cat image as placeholder
    text: "23 năm trước, có một em bé ra đời...",
    title: "🎂 Once Upon a Time...",
  },
  {
    image: "/meo2.png", // Use existing cat image as placeholder
    text: "Cô ấy lớn lên, dần dần, dần dần",
    title: "💫 Growing Up...",
  },
  {
    image: "/bo.png", // Use existing cow image for the cow joke!
    text: "Khi gặp tôi, chúng tôi đứng chung một khung hình thì sẽ luôn có 1 người 1 bò. Nhưng cô ấy là người còn tôi là bò :(",
    title: "🐄 The Perfect Duo...",
  },
  // ... rest of the pages
];
```
