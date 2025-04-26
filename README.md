# Stable Diffusion XL Image Generator & Refiner
A Python class for generating and refining images using Stable Diffusion XL (base + refiner models).

Features
🖼️ Image Generation: Create images from text prompts using StableDiffusionXLPipeline

✨ Image Refinement: Enhance generated/existing images with StableDiffusionXLImg2ImgPipeline

🛠️ Customizable: Adjust parameters like guidance_scale, strength, resolution, etc.

💾 Memory Management: Automatic model unloading and GPU cleanup

✅ Error Handling: Graceful failure with error messages

Usage
python
from visualizer import Visualizer

# Initialize with model IDs (e.g., "stabilityai/stable-diffusion-xl-base-1.0")
visualizer = Visualizer(base_model_id, refiner_model_id)

# Generate an image
image = visualizer.create_image(
    prompt="A futuristic cityscape", 
    negative_prompt="blurry, distorted", 
    save_image=True,
    path_to_save="city.png"
)

# Refine the image
refined_image = visualizer.refine_image(
    prompt="Add neon lights", 
    strength=0.3,
    image_path="city.png"
)
Key Parameters
prompt: Text description of the desired image

negative_prompt: Elements to exclude (e.g., "blurry, low quality")

strength (refinement): How much to alter the image (0–1)

guidance_scale: Adherence to the prompt (higher = stricter)

Requirements
Python 3.8+

PyTorch

diffusers library

CUDA (for GPU acceleration)

Install dependencies:

bash
pip install torch diffusers pillow
Roadmap
Basic generation/refinement

Support for custom-trained models

GUI integration

Developed by Timur Gilmutdinov 
@Space_crab_mut
