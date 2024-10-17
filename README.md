# Bobs FLUX/SDXL Latent Optimizer Node

This custom node for ComfyUI is designed to optimize latent generation for use with both FLUX and SDXL modes. It provides flexible control over aspect ratios, megapixel sizes, and upscale factors, allowing users to dynamically create latents that fit specific tiling and resolution needs.

## Features

- **Custom Aspect Ratio Input**: Enter any aspect ratio in the format `x:y`. This allows for total control over the image dimensions.
- **Megapixel Size Selection**: Choose from different megapixel sizes (1, 1.25, 1.5, 1.75, and 2 MP) to adjust the resolution dynamically.
- **Upscale Factor**: Specify an upscale factor to ensure proper scaling of the latent image.
- **Mode Switch (FLUX/SDXL)**: Select between FLUX or SDXL modes for optimal latent generation and tiling. SDXL mode rounds dimensions to the closest SDXL resolution.
- **Automatic Tile Calculation**: The node automatically calculates tile dimensions to ensure the generated latent is split into 4 tiles after upscaling.

## Installation

1. Download the `.py` file [Bobs_FLUX_SDXL_Latent_Optimizer.py](path-to-your-node-file).
2. Place the file in the `custom_nodes` folder of your ComfyUI installation.
3. Restart ComfyUI to load the node.

## Inputs

- **Aspect Ratio**: Enter an aspect ratio in the format `x:y`. Example: `16:9` for a widescreen aspect ratio.
- **Megapixel Size**: Select the resolution size based on megapixels. Options include `1`, `1.25`, `1.5`, `1.75`, and `2`.
- **Upscale Factor**: A float value to define the upscaling factor.
- **Mode**: Choose between `FLUX` and `SDXL`. This changes how the resolution is rounded and handled.

## Outputs

- **Latent**: The generated latent image based on the provided resolution and aspect ratio.
- **Tile Width/Height**: The dimensions of the tiles after upscaling.
- **Upscale Factor**: The factor by which the image was upscaled.

## Example Usage

In the ComfyUI workflow, insert this node where you need to generate a latent with a specific resolution and aspect ratio. Pass the latent to an upscaling node (such as UltimateSDUpscale) for further processing.

```plaintext
[Latent] --> [Bobs FLUX/SDXL Latent Optimizer] --> [Upscaling Node]
```

## Contributions

Feel free to submit issues or pull requests to improve the node. Any feedback or suggestions are welcome!

## License

This project is licensed under the MIT License.

---

Feel free to modify or expand on this draft to suit your preferences. Let me know if you need any changes!
