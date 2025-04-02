---
slug: /
sidebar_position: 1
---
# generateSprite Documentation

## Brief Description
`generateSprite` is a function that generates a sprite sheet image based on a given description, using AI-powered image generation and analysis.

## Usage
To use `generateSprite`, import it from the sprite module and call it with a description of the character you want to generate.

```javascript
import { sprite } from './path/to/sprite/module';

const result = await sprite.generateSprite(description, options);
```

## Parameters
- `description` (string, required): A text description of the character to generate.
- `options` (object, optional):
  - `iterations` (number): Number of sprite variations to generate (default: 1).
  - `size` (string): Size of the generated image (default: "1024x1024").
  - `save` (boolean): Whether to save the generated image to disk (default: false).
  - `characterDescription` (string): Additional character description for GPT analysis.
  - `realisticMode` (boolean): Whether to generate more realistic images (default: false).

## Return Value
Returns an object or array of objects containing:
- `messages`: JSON object with frameHeight, frameWidth, and other sprite information.
- `image`: Base64-encoded image data URL of the generated sprite sheet.
- `pngBuffer`: PNG buffer of the generated sprite sheet.

## Examples

1. Generate a single sprite sheet:
```javascript
const result = await sprite.generateSprite("A pixelated robot");
console.log(result.messages);
console.log(result.image);
```

2. Generate multiple variations:
```javascript
const variations = await sprite.generateSprite("A cartoon cat", { iterations: 3 });
variations.forEach((variation, index) => {
  console.log(`Variation ${index + 1}:`, variation.messages);
});
```

3. Generate a realistic sprite:
```javascript
const realisticSprite = await sprite.generateSprite("A detailed warrior", { realisticMode: true });
console.log(realisticSprite.messages);
```

## Notes or Considerations
- The function uses AI models (DALL-E 3 and GPT-4) to generate and analyze images, which may result in varying outputs for the same input.
- Generated sprites are optimized for walking animations and follow a specific layout (6 frames in a 2x3 grid).
- The function converts images to grayscale for better consistency in sprite sheets.
- When saving images, they are stored in an 'assets' folder with a filename based on the description.
- The function may take some time to complete due to API calls and image processing.
- The `realisticMode` option allows for generating more detailed and realistic sprites, which may be suitable for different art styles or game genres.
- The `characterDescription` option can be used to provide additional context for GPT analysis, potentially improving the accuracy of sprite information.
