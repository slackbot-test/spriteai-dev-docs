# SpriteAI Quick Start Guide

This guide will help you quickly get started with using SpriteAI to generate custom sprites for your projects.

## Prerequisites

- A valid API key for SpriteAI
- Python 3.7 or higher installed on your system
- Basic knowledge of Python and command-line operations

## Installation

1. Install the SpriteAI Python package using pip:

   ```
   pip install spriteai
   ```

2. Set up your API key as an environment variable:

   ```
   export SPRITEAI_API_KEY=your_api_key_here
   ```

   Replace `your_api_key_here` with your actual SpriteAI API key.

## Basic Usage

Here's a simple example to generate a sprite using SpriteAI:

```python
from spriteai import generate_sprite

# Define sprite parameters
params = {
    'prompt': 'A cute cartoon cat',
    'style': 'pixel art',
    'size': '64x64',
    'format': 'png'
}

# Generate the sprite
sprite_data = generate_sprite(params)

# Save the sprite to a file
with open('cat_sprite.png', 'wb') as f:
    f.write(sprite_data)

print('Sprite generated and saved as cat_sprite.png')
```

This script will generate a 64x64 pixel art sprite of a cute cartoon cat and save it as `cat_sprite.png` in your current directory.

## Customizing Your Sprite

You can customize your sprite by adjusting the parameters in the `params` dictionary:

- `prompt`: Describe the sprite you want to generate
- `style`: Specify the artistic style (e.g., 'pixel art', 'watercolor', '3D')
- `size`: Set the dimensions of the sprite (e.g., '32x32', '128x128')
- `format`: Choose the output format ('png' or 'jpg')

## Next Steps

- Explore more advanced options in the full [SpriteAI documentation](https://docs.spriteai.com)
- Try generating different types of sprites for your projects
- Experiment with various styles and prompts to achieve desired results

Happy sprite generating with SpriteAI!