
# ComfyUI Essentials mb

## About

This repo fork from [ComfyUI_essentials](https://github.com/cubiq/ComfyUI_essentials)

Thanks to [cubiq](https://github.com/cubiq) for the original repo.

## Nodes

<details>
<summary>### Image Analysis</summary>

- 🔧 Image Enhance Difference
  - Inputs:
    - image (IMAGE)
    - image2 (IMAGE)
    - exponent (FLOAT, default: 0.75, min: 0.00, max: 1.00, step: 0.05)
  - Outputs:
    - IMAGE
</details>

<details>
<summary>### Image Batch</summary>

- 🔧 Images Batch Multiple
  - Inputs:
    - image_1 (IMAGE)
    - method ("nearest-exact", "bilinear", "area", "bicubic", "lanczos", default: "lanczos")
    - image_2 (IMAGE, optional)
    - image_3 (IMAGE, optional)
    - image_4 (IMAGE, optional)
    - image_5 (IMAGE, optional)
  - Outputs:
    - IMAGE

- 🔧 Image Expand Batch
  - Inputs:
    - image (IMAGE)
    - size (INT, default: 16, min: 1, step: 1)
    - method ("expand", "repeat all", "repeat first", "repeat last")
  - Outputs:
    - IMAGE

- 🔧 Image From Batch
  - Inputs:
    - image (IMAGE)
    - start (INT, default: 0, min: 0, step: 1)
    - length (INT, default: -1, min: -1, step: 1)
  - Outputs:
    - IMAGE

- 🔧 Image List To Batch
  - Inputs:
    - image (IMAGE, list)
  - Outputs:
    - IMAGE

- 🔧 Image Batch To List
  - Inputs:
    - image (IMAGE)
  - Outputs:
    - IMAGE (list)
</details>

<details>
<summary>### Image Manipulation</summary>

- 🔧 Image Composite From Mask Batch
  - Inputs:
    - image_from (IMAGE)
    - image_to (IMAGE)
    - mask (MASK)
  - Outputs:
    - IMAGE

- 🔧 Image Composite
  - Inputs:
    - destination (IMAGE)
    - source (IMAGE)
    - x (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - y (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - offset_x (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - offset_y (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - mask (MASK, optional)
  - Outputs:
    - IMAGE

- 🔧 Image Crop
  - Inputs:
    - image (IMAGE)
    - width (INT, default: 256, min: 0, max: 18446744073709551615, step: 8)
    - height (INT, default: 256, min: 0, max: 18446744073709551615, step: 8)
    - position ("top-left", "top-center", "top-right", "right-center", "bottom-right", "bottom-center", "bottom-left", "left-center", "center")
    - x_offset (INT, default: 0, min: -99999, step: 1)
    - y_offset (INT, default: 0, min: -99999, step: 1)
  - Outputs:
    - IMAGE
    - x (INT)
    - y (INT)

- 🔧 Image Flip
  - Inputs:
    - image (IMAGE)
    - axis ("x", "y", "xy")
  - Outputs:
    - IMAGE

- 🔧 Image Random Transform
  - Inputs:
    - image (IMAGE)
    - seed (INT, default: 0, min: 0, max: 18446744073709551615)
    - repeat (INT, default: 1, min: 1, max: 256, step: 1)
    - variation (FLOAT, default: 0.1, min: 0.0, max: 1.0, step: 0.05)
  - Outputs:
    - IMAGE

- 🔧 Image Remove Alpha
  - Inputs:
    - image (IMAGE)
  - Outputs:
    - IMAGE

- 🔧 Image Remove Background
  - Inputs:
    - rembg_session (REMBG_SESSION)
    - image (IMAGE)
  - Outputs:
    - IMAGE
    - MASK

- 🔧 Image Resize
  - Inputs:
    - image (IMAGE)
    - width (INT, default: 512, min: 0, max: 18446744073709551615, step: 1)
    - height (INT, default: 512, min: 0, max: 18446744073709551615, step: 1)
    - interpolation ("nearest", "bilinear", "bicubic", "area", "nearest-exact", "lanczos")
    - method ("stretch", "keep proportion", "fill / crop", "pad")
    - condition ("always", "downscale if bigger", "upscale if smaller", "if bigger area", "if smaller area")
    - multiple_of (INT, default: 0, min: 0, max: 512, step: 1)
  - Outputs:
    - IMAGE
    - width (INT)
    - height (INT)

- 🔧 Image Seam Carving
  - Inputs:
    - image (IMAGE)
    - width (INT, default: 512, min: 1, max: 18446744073709551615, step: 1)
    - height (INT, default: 512, min: 1, max: 18446744073709551615, step: 1)
    - energy ("backward", "forward")
    - order ("width-first", "height-first")
    - keep_mask (MASK, optional)
    - drop_mask (MASK, optional)
  - Outputs:
    - IMAGE

- 🔧 Image Tile
  - Inputs:
    - image (IMAGE)
    - rows (INT, default: 2, min: 1, max: 256, step: 1)
    - cols (INT, default: 2, min: 1, max: 256, step: 1)
    - overlap (FLOAT, default: 0, min: 0, max: 0.5, step: 0.01)
    - overlap_x (INT, default: 0, min: 0, max: 9223372036854775807, step: 1)
    - overlap_y (INT, default: 0, min: 0, max: 9223372036854775807, step: 1)
  - Outputs:
    - IMAGE
    - tile_width (INT)
    - tile_height (INT)
    - overlap_x (INT)
    - overlap_y (INT)

- 🔧 Image Untile
  - Inputs:
    - tiles (IMAGE)
    - overlap_x (INT, default: 0, min: 0, max: 9223372036854775807, step: 1)
    - overlap_y (INT, default: 0, min: 0, max: 9223372036854775807, step: 1)
    - rows (INT, default: 2, min: 1, max: 256, step: 1)
    - cols (INT, default: 2, min: 1, max: 256, step: 1)
  - Outputs:
    - IMAGE

- 🔧 RemBG Session
  - Inputs:
    - model ("u2net: general purpose", "u2netp: lightweight general purpose", "u2net_human_seg: human segmentation", "u2net_cloth_seg: cloths Parsing", "silueta: very small u2net", "isnet-general-use: general purpose", "isnet-anime: anime illustrations", "sam: general purpose")
    - providers ("CPU", "CUDA", "ROCM", "DirectML", "OpenVINO", "CoreML", "Tensorrt", "Azure")
  - Outputs:
    - REMBG_SESSION

- 🔧 InSPyReNet TransparentBG
  - Inputs:
    - mode ("base", "fast", "base-nightly")
    - use_jit (BOOLEAN, default: True)
  - Outputs:
    - REMBG_SESSION
</details>

<details>
<summary>### Image Processing</summary>

- 🔧 Image Apply LUT
  - Inputs:
    - image (IMAGE)
    - lut_file (selected from luts folder)
    - gamma_correction (BOOLEAN, default: True)
    - clip_values (BOOLEAN, default: True)
    - strength (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.1)
  - Outputs:
    - IMAGE

- 🔧 Image Contrast Adaptive Sharpening
  - Inputs:
    - image (IMAGE)
    - amount (FLOAT, default: 0.8, min: 0, max: 1, step: 0.05)
  - Outputs:
    - IMAGE

- 🔧 Image Desaturate
  - Inputs:
    - image (IMAGE)
    - factor (FLOAT, default: 1.00, min: 0.00, max: 1.00, step: 0.05)
    - method ("luminance (Rec.709)", "luminance (Rec.601)", "average", "lightness")
  - Outputs:
    - IMAGE

- 🔧 Pixelize
  - Inputs:
    - image (IMAGE)
    - downscale_mode ("contrast", "bicubic", "nearest", "center", "k-centroid")
    - target_size (INT, default: 128, min: 0, max: 18446744073709551615, step: 8)
    - patch_size (INT, default: 16, min: 4, max: 32, step: 2)
    - thickness (INT, default: 2, min: 1, max: 16, step: 1)
    - color_matching (BOOLEAN, default: True)
    - upscale (BOOLEAN, default: True)
  - Outputs:
    - IMAGE

- 🔧 Image Posterize
  - Inputs:
    - image (IMAGE)
    - threshold (FLOAT, default: 0.50, min: 0.00, max: 1.00, step: 0.05)
  - Outputs:
    - IMAGE

- 🔧 Image Color Match
  - Inputs:
    - image (IMAGE)
    - reference (IMAGE)
    - color_space ("LAB", "YCbCr", "RGB", "LUV", "YUV", "XYZ")
    - factor (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.05)
    - device ("auto", "cpu", "gpu")
    - batch_size (INT, default: 0, min: 0, max: 1024, step: 1)
    - reference_mask (MASK, optional)
  - Outputs:
    - IMAGE

- 🔧 Image Color Match Adobe
  - Inputs:
    - image (IMAGE)
    - reference (IMAGE)
    - color_space ("RGB", "LAB")
    - luminance_factor (FLOAT, default: 1.0, min: 0.0, max: 2.0, step: 0.05)
    - color_intensity_factor (FLOAT, default: 1.0, min: 0.0, max: 2.0, step: 0.05)
    - fade_factor (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.05)
    - neutralization_factor (FLOAT, default: 0.0, min: 0.0, max: 1.0, step: 0.05)
    - device ("auto", "cpu", "gpu")
    - reference_mask (MASK, optional)
  - Outputs:
    - IMAGE

- 🔧 Image Histogram Match
  - Inputs:
    - image (IMAGE)
    - reference (IMAGE)
    - method ("pytorch", "skimage")
    - factor (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.05)
    - device ("auto", "cpu", "gpu")
  - Outputs:
    - IMAGE

- 🔧 Image Smart Sharpen
  - Inputs:
    - image (IMAGE)
    - noise_radius (INT, default: 7, min: 1, max: 25, step: 1)
    - preserve_edges (FLOAT, default: 0.75, min: 0.0, max: 1.0, step: 0.05)
    - sharpen (FLOAT, default: 5.0, min: 0.0, max: 25.0, step: 0.5)
    - ratio (FLOAT, default: 0.5, min: 0.0, max: 1.0, step: 0.1)
  - Outputs:
    - IMAGE
</details>

<details>
<summary>### Image Utilities</summary>

- 🔧 Get Image Size
  - Inputs:
    - image (IMAGE)
  - Outputs:
    - width (INT)
    - height (INT)
    - count (INT)

- 🔧 Image To Device
  - Inputs:
    - image (IMAGE)
    - device ("auto", "cpu", "gpu")
  - Outputs:
    - IMAGE

- 🔧 Image Preview From Latent
  - Inputs:
    - latent (LATENT)
    - vae (VAE)
    - tile_size (INT, default: 0, min: 0, max: 4096, step: 64)
    - image ("none", optional)
    - prompt (hidden)
    - extra_pnginfo (hidden)
  - Outputs:
    - IMAGE
    - MASK
    - width (INT)
    - height (INT)

- 🔧 Noise From Image
  - Inputs:
    - image (IMAGE)
    - noise_strenght (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.01)
    - noise_size (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.01)
    - color_noise (FLOAT, default: 0.2, min: 0.0, max: 1.0, step: 0.01)
    - mask_strength (FLOAT, default: 0.5, min: 0.0, max: 1.0, step: 0.01)
    - mask_scale_diff (FLOAT, default: 0.0, min: 0.0, max: 1.0, step: 0.01)
    - mask_contrast (FLOAT, default: 1.0, min: 0.0, max: 100.0, step: 0.1)
    - saturation (FLOAT, default: 2.0, min: 0.0, max: 100.0, step: 0.1)
    - contrast (FLOAT, default: 1.0, min: 0.0, max: 100.0, step: 0.1)
    - blur (FLOAT, default: 1.0, min: 0.0, max: 10.0, step: 0.1)
    - noise_mask (IMAGE, optional)
  - Outputs:
    - IMAGE
</details>

<details>
<summary>### Mask</summary>

- 🔧 Mask Blur
  - Inputs:
    - mask (MASK)
    - amount (INT, default: 6, min: 0, max: 256, step: 1)
    - device ("auto", "cpu", "gpu")
  - Outputs:
    - MASK

- 🔧 Mask Fix
  - Inputs:
    - mask (MASK)
    - erode_dilate (INT, default: 0, min: -256, max: 256, step: 1)
    - fill_holes (INT, default: 0, min: 0, max: 128, step: 1)
    - remove_isolated_pixels (INT, default: 0, min: 0, max: 32, step: 1)
    - smooth (INT, default: 0, min: 0, max: 256, step: 1)
    - blur (INT, default: 0, min: 0, max: 256, step: 1)
  - Outputs:
    - MASK

- 🔧 Mask Flip
  - Inputs:
    - mask (MASK)
    - axis ("x", "y", "xy")
  - Outputs:
    - MASK

- 🔧 Mask From Color
  - Inputs:
    - image (IMAGE)
    - red (INT, default: 255, min: 0, max: 255, step: 1)
    - green (INT, default: 255, min: 0, max: 255, step: 1)
    - blue (INT, default: 255, min: 0, max: 255, step: 1)
    - threshold (INT, default: 0, min: 0, max: 127, step: 1)
  - Outputs:
    - MASK

- 🔧 Mask From List
  - Inputs:
    - width (INT, default: 32, min: 0, max: 18446744073709551615, step: 8)
    - height (INT, default: 32, min: 0, max: 18446744073709551615, step: 8)
    - values (any, default: 0.0, min: 0.0, max: 1.0, optional)
    - str_values (STRING, multiline, placeholder: "0.0, 0.5, 1.0", optional)
  - Outputs:
    - MASK

- 🔧 Mask From RGB/CMY/BW
  - Inputs:
    - image (IMAGE)
    - threshold_r (FLOAT, default: 0.15, min: 0.0, max: 1, step: 0.01)
    - threshold_g (FLOAT, default: 0.15, min: 0.0, max: 1, step: 0.01)
    - threshold_b (FLOAT, default: 0.15, min: 0.0, max: 1, step: 0.01)
  - Outputs:
    - red (MASK)
    - green (MASK)
    - blue (MASK)
    - cyan (MASK)
    - magenta (MASK)
    - yellow (MASK)
    - black (MASK)
    - white (MASK)

- 🔧 Mask From Segmentation
  - Inputs:
    - image (IMAGE)
    - segments (INT, default: 6, min: 1, max: 16, step: 1)
    - remove_isolated_pixels (INT, default: 0, min: 0, max: 32, step: 1)
    - remove_small_masks (FLOAT, default: 0.0, min: 0.0, max: 1.0, step: 0.01)
    - fill_holes (BOOLEAN, default: False)
  - Outputs:
    - MASK

- 🔧 Mask Preview
  - Inputs:
    - mask (MASK)
    - prompt (hidden)
    - extra_pnginfo (hidden)
  - Outputs:
    - Saved image preview

- 🔧 Mask Bounding Box
  - Inputs:
    - mask (MASK)
    - padding (INT, default: 0, min: 0, max: 4096, step: 1)
    - blur (INT, default: 0, min: 0, max: 256, step: 1)
    - image_optional (IMAGE, optional)
  - Outputs:
    - MASK
    - IMAGE
    - x (INT)
    - y (INT)
    - width (INT)
    - height (INT)

- 🔧 Mask Smooth
  - Inputs:
    - mask (MASK)
    - amount (INT, default: 0, min: 0, max: 127, step: 1)
  - Outputs:
    - MASK

- 🔧 Transition Mask
  - Inputs:
    - width (INT, default: 512, min: 1, max: 18446744073709551615, step: 1)
    - height (INT, default: 512, min: 1, max: 18446744073709551615, step: 1)
    - frames (INT, default: 16, min: 1, max: 9999, step: 1)
    - start_frame (INT, default: 0, min: 0, step: 1)
    - end_frame (INT, default: 9999, min: 0, step: 1)
    - transition_type ("horizontal slide", "vertical slide", "horizontal bar", "vertical bar", "center box", "horizontal door", "vertical door", "circle", "fade")
    - timing_function ("linear", "in", "out", "in-out")
  - Outputs:
    - MASK
</details>

<details>
<summary>### Mask Batch</summary>

- 🔧 Mask Batch
  - Inputs:
    - mask1 (MASK)
    - mask2 (MASK)
  - Outputs:
    - MASK

- 🔧 Mask Expand Batch
  - Inputs:
    - mask (MASK)
    - size (INT, default: 16, min: 1, step: 1)
    - method ("expand", "repeat all", "repeat first", "repeat last")
  - Outputs:
    - MASK

- 🔧 Mask From Batch
  - Inputs:
    - mask (MASK)
    - start (INT, default: 0, min: 0, step: 1)
    - length (INT, default: 1, min: 1, step: 1)
  - Outputs:
    - MASK
</details>

<details>
<summary>### Sampling</summary>

- 🔧 KSampler Stochastic Variations
  - Inputs:
    - model (MODEL)
    - latent_image (LATENT)
    - noise_seed (INT, default: 0, min: 0, max: 18446744073709551615)
    - steps (INT, default: 25, min: 1, max: 10000)
    - cfg (FLOAT, default: 7.0, min: 0.0, max: 100.0, step: 0.1, round: 0.01)
    - sampler (comfy.samplers.KSampler.SAMPLERS)
    - scheduler (comfy.samplers.KSampler.SCHEDULERS)
    - positive (CONDITIONING)
    - negative (CONDITIONING)
    - variation_seed (INT:seed, default: 0, min: 0, max: 18446744073709551615)
    - variation_strength (FLOAT, default: 0.2, min: 0.0, max: 1.0, step: 0.05, round: 0.01)
    - cfg_scale (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.05, round: 0.01)
  - Outputs:
    - LATENT

- 🔧 KSampler Variations with Noise Injection
  - Inputs:
    - model (MODEL)
    - latent_image (LATENT)
    - main_seed (INT:seed, default: 0, min: 0, max: 18446744073709551615)
    - steps (INT, default: 20, min: 1, max: 10000)
    - cfg (FLOAT, default: 8.0, min: 0.0, max: 100.0, step: 0.1, round: 0.01)
    - sampler_name (comfy.samplers.KSampler.SAMPLERS)
    - scheduler (comfy.samplers.KSampler.SCHEDULERS)
    - positive (CONDITIONING)
    - negative (CONDITIONING)
    - variation_strength (FLOAT, default: 0.17, min: 0.0, max: 1.0, step: 0.01, round: 0.01)
    - variation_seed (INT:seed, default: 12345, min: 0, max: 18446744073709551615)
    - denoise (FLOAT, default: 1.0, min: 0.0, max: 1.0, step: 0.01, round: 0.01)
  - Outputs:
    - LATENT

- 🔧 Inject Latent Noise
  - Inputs:
    - latent (LATENT)
    - noise_seed (INT, default: 0, min: 0, max: 18446744073709551615)
    - noise_strength (FLOAT, default: 1.0, min: -20.0, max: 20.0, step: 0.01, round: 0.01)
    - normalize ("false", "true", default: "false")
    - mask (MASK, optional)
  - Outputs:
    - LATENT

- 🔧 Flux Sampler Parameters
  - Inputs:
    - model (MODEL)
    - conditioning (CONDITIONING)
    - latent_image (LATENT)
    - seed (STRING, default: "?")
    - sampler (STRING, default: "euler")
    - scheduler (STRING, default: "simple")
    - steps (STRING, default: "20")
    - guidance (STRING, default: "3.5")
    - max_shift (STRING)
    - base_shift (STRING)
    - denoise (STRING, default: "1.0")
    - loras (LORA_PARAMS, optional)
  - Outputs:
    - latent (LATENT)
    - params (SAMPLER_PARAMS)

- 🔧 Guidance Timestep (experimental)
  - Inputs:
    - model (MODEL)
    - value (FLOAT, default: 2.0, min: 0.0, max: 100.0, step: 0.05)
    - start_at (FLOAT, default: 0.2, min: 0.0, max: 1.0, step: 0.01)
    - end_at (FLOAT, default: 0.8, min: 0.0, max: 1.0, step: 0.01)
  - Outputs:
    - MODEL

- 🔧 Plot Sampler Parameters
  - Inputs:
    - images (IMAGE)
    - params (SAMPLER_PARAMS)
    - order_by ("none", "time", "seed", "steps", "denoise", "sampler", "scheduler", "guidance", "max_shift", "base_shift", "lora_strength")
    - cols_value ("none", "time", "seed", "steps", "denoise", "sampler", "scheduler", "guidance", "max_shift", "base_shift", "lora_strength")
    - cols_num (INT, default: -1, min: -1, max: 1024)
    - add_prompt ("false", "true", "excerpt")
    - add_params ("false", "true", "changes only", default: "true")
  - Outputs:
    - IMAGE

- 🔧Text Encode for Sampler Params
  - Inputs:
    - text (STRING, multiline, dynamicPrompts, default: "Separate prompts with at least three dashes\n---\nLike so")
    - clip (CLIP)
  - Outputs:
    - CONDITIONING

- 🔧 Sampler Select Helper
  - Inputs:
    - All KSampler samplers as BOOLEAN options
  - Outputs:
    - STRING

- 🔧 Scheduler Select Helper
  - Inputs:
    - All KSampler schedulers as BOOLEAN options
  - Outputs:
    - STRING

- 🔧 LoRA for Flux Parameters
  - Inputs:
    - lora_1 (selected from loras folder)
    - strength_model_1 (STRING, multiline: False, dynamicPrompts: False, default: "1.0")
  - Outputs:
    - LORA_PARAMS

- 🔧 Model Sampling SD3 Advanced
  - Inputs:
    - model (MODEL)
    - shift (FLOAT, default: 3.0, min: 0.0, max: 100.0, step: 0.01)
    - cut_off (FLOAT, default: 0.5, min: 0.0, max: 1.0, step: 0.05)
    - shift_multiplier (FLOAT, default: 2, min: 0, max: 10, step: 0.05)
  - Outputs:
    - MODEL
</details>

<details>
<summary>### Segmentation</summary>

- 🔧 Apply CLIPSeg
  - Inputs:
    - clip_seg (CLIP_SEG)
    - image (IMAGE)
    - prompt (STRING, multiline: False, default: "")
    - threshold (FLOAT, default: 0.4, min: 0.0, max: 1.0, step: 0.05)
    - smooth (INT, default: 9, min: 0, max: 32, step: 1)
    - dilate (INT, default: 0, min: -32, max: 32, step: 1)
    - blur (INT, default: 0, min: 0, max: 64, step: 1)
  - Outputs:
    - MASK

- 🔧 Load CLIPSeg Models
  - Inputs:
    - None
  - Outputs:
    - CLIP_SEG
</details>

<details>
<summary>### Utilities</summary>

- 🔧 Batch Count
  - Inputs:
    - batch (any)
  - Outputs:
    - INT

- 🔧 Console Debug
  - Inputs:
    - value (any)
    - prefix (STRING, multiline: False, default: "Value:")
  - Outputs:
    - None (prints to console)

- 🔧 Debug Tensor Shape
  - Inputs:
    - tensor (any)
  - Outputs:
    - None (prints tensor shapes to console)

- 🔧 Display Any
  - Inputs:
    - input (any)
    - mode ("raw value", "tensor shape")
  - Outputs:
    - STRING

- 🔧 Model Compile
  - Inputs:
    - model (MODEL)
    - fullgraph (BOOLEAN, default: False)
    - dynamic (BOOLEAN, default: False)
    - mode ("default", "reduce-overhead", "max-autotune", "max-autotune-no-cudagraphs")
  - Outputs:
    - MODEL

- 🔧 Remove Latent Mask
  - Inputs:
    - samples (LATENT)
  - Outputs:
    - LATENT

- 🔧 Empty Latent Size Picker
  - Inputs:
    - resolution (various standard resolutions)
    - batch_size (INT, default: 1, min: 1, max: 4096)
    - width_override (INT, default: 0, min: 0, max: 18446744073709551615, step: 8)
    - height_override (INT, default: 0, min: 0, max: 18446744073709551615, step: 8)
  - Outputs:
    - LATENT
    - width (INT)
    - height (INT)

- 🔧 Simple Comparison
  - Inputs:
    - a (any, default: 0)
    - b (any, default: 0)
    - comparison ("==", "!=", "<", "<=", ">", ">=")
  - Outputs:
    - BOOLEAN

- 🔧 Simple Condition
  - Inputs:
    - evaluate (any, default: 0)
    - on_true (any, default: 0)
    - on_false (any, optional, default: None)
  - Outputs:
    - result (any)

- 🔧 Simple Math
  - Inputs:
    - a (any, optional, default: 0.0)
    - b (any, optional, default: 0.0)
    - c (any, optional, default: 0.0)
    - value (STRING, multiline: False, default: "")
  - Outputs:
    - int (INT)
    - float (FLOAT)

- 🔧 Simple Math Dual
  - Inputs:
    - a (any, optional, default: 0.0)
    - b (any, optional, default: 0.0)
    - c (any, optional, default: 0.0)
    - d (any, optional, default: 0.0)
    - value_1 (STRING, multiline: False, default: "")
    - value_2 (STRING, multiline: False, default: "")
  - Outputs:
    - int_1 (INT)
    - float_1 (FLOAT)
    - int_2 (INT)
    - float_2 (FLOAT)

- 🔧 Simple Math Condition
  - Inputs:
    - evaluate (any, default: 0)
    - on_true (STRING, multiline: False, default: "")
    - on_false (STRING, multiline: False, default: "")
    - a (any, optional, default: 0.0)
    - b (any, optional, default: 0.0)
    - c (any, optional, default: 0.0)
  - Outputs:
    - INT
    - FLOAT

- 🔧 Simple Math Boolean
  - Inputs:
    - value (BOOLEAN, default: False)
  - Outputs:
    - BOOLEAN
    - int (INT)

- 🔧 Simple Math Float
  - Inputs:
    - value (FLOAT, default: 0.0, min: -18446744073709551615, max: 18446744073709551615, step: 0.05)
  - Outputs:
    - FLOAT

- 🔧 Simple Math Int
  - Inputs:
    - value (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
  - Outputs:
    - INT

- 🔧 Simple Math Percent
  - Inputs:
    - value (FLOAT, default: 0.0, min: 0, max: 1, step: 0.05)
  - Outputs:
    - FLOAT

- 🔧 Simple Math Slider
  - Inputs:
    - value (FLOAT, display: slider, default: 0.5, min: 0.0, max: 1.0, step: 0.001)
    - min (FLOAT, default: 0.0, min: -18446744073709551615, max: 18446744073709551615, step: 0.001)
    - max (FLOAT, default: 1.0, min: -18446744073709551615, max: 18446744073709551615, step: 0.001)
    - rounding (INT, default: 0, min: 0, max: 10, step: 1)
  - Outputs:
    - FLOAT
    - INT

- 🔧 Simple Math Slider low-res
  - Inputs:
    - value (INT, display: slider, default: 5, min: 0, max: 10, step: 1)
    - min (FLOAT, default: 0.0, min: -18446744073709551615, max: 18446744073709551615, step: 0.001)
    - max (FLOAT, default: 1.0, min: -18446744073709551615, max: 18446744073709551615, step: 0.001)
    - rounding (INT, default: 0, min: 0, max: 10, step: 1)
  - Outputs:
    - FLOAT
    - INT
</details>

<details>
<summary>### Conditioning</summary>

- 🔧 SDXL CLIPTextEncode
  - Inputs:
    - width (INT, default: 1024.0, min: 0, max: 18446744073709551615)
    - height (INT, default: 1024.0, min: 0, max: 18446744073709551615)
    - size_cond_factor (INT, default: 4, min: 1, max: 16)
    - text (STRING, multiline: True, dynamicPrompts: True, default: "")
    - clip (CLIP)
  - Outputs:
    - CONDITIONING

- 🔧 Cond Combine Multiple
  - Inputs:
    - conditioning_1 (CONDITIONING)
    - conditioning_2 (CONDITIONING)
    - conditioning_3 (CONDITIONING, optional)
    - conditioning_4 (CONDITIONING, optional)
    - conditioning_5 (CONDITIONING, optional)
  - Outputs:
    - CONDITIONING

- 🔧 SD3 Negative Conditioning
  - Inputs:
    - conditioning (CONDITIONING)
    - end (FLOAT, default: 0.1, min: 0.0, max: 1.0, step: 0.001)
  - Outputs:
    - CONDITIONING

- 🔧 Flux Attention Seeker
  - Inputs:
    - clip (CLIP)
    - apply_to_query (BOOLEAN, default: True)
    - apply_to_key (BOOLEAN, default: True)
    - apply_to_value (BOOLEAN, default: True)
    - apply_to_out (BOOLEAN, default: True)
    - clip_l_0 through clip_l_11 (FLOAT sliders, default: 1.0, min: 0, max: 5, step: 0.05)
    - t5xxl_0 through t5xxl_23 (FLOAT sliders, default: 1.0, min: 0, max: 5, step: 0.05)
  - Outputs:
    - CLIP

- 🔧 SD3 Attention Seeker L/G
  - Inputs:
    - clip (CLIP)
    - apply_to_query (BOOLEAN, default: True)
    - apply_to_key (BOOLEAN, default: True)
    - apply_to_value (BOOLEAN, default: True)
    - apply_to_out (BOOLEAN, default: True)
    - clip_l_0 through clip_l_11 (FLOAT sliders, default: 1.0, min: 0, max: 5, step: 0.05)
    - clip_g_0 through clip_g_31 (FLOAT sliders, default: 1.0, min: 0, max: 5, step: 0.05)
  - Outputs:
    - CLIP

- 🔧 SD3 Attention Seeker T5
  - Inputs:
    - clip (CLIP)
    - apply_to_query (BOOLEAN, default: True)
    - apply_to_key (BOOLEAN, default: True)
    - apply_to_value (BOOLEAN, default: True)
    - apply_to_out (BOOLEAN, default: True)
    - t5xxl_0 through t5xxl_23 (FLOAT sliders, default: 1.0, min: 0, max: 5, step: 0.05)
  - Outputs:
    - CLIP

- 🔧 Flux Model Blocks Buster
  - Inputs:
    - model (MODEL)
    - blocks (STRING, multiline: True, dynamicPrompts: True)
  - Outputs:
    - MODEL
    - patched_blocks (STRING)
</details>

<details>
<summary>### Text</summary>

- 🔧 Draw Text
  - Inputs:
    - text (STRING, multiline: True, dynamicPrompts: True, default: "Hello, World!")
    - font (sorted list of .ttf and .otf files in fonts directory)
    - size (INT, default: 56, min: 1, max: 9999, step: 1)
    - color (COLOR, default: "#FFFFFF")
    - alpha (INT, default: 255, min: 0, max: 255, step: 1)
    - background_color (COLOR, default: "#000000")
    - background_alpha (INT, default: 0, min: 0, max: 255, step: 1)
    - shadow_distance (INT, default: 0, min: 0, max: 100, step: 1)
    - shadow_blur (INT, default: 0, min: 0, max: 100, step: 1)
    - shadow_color (STRING, multiline: False, default: "#000000")
    - horizontal_align ("left", "center", "right")
    - vertical_align ("top", "center", "bottom")
    - offset_x (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - offset_y (INT, default: 0, min: -18446744073709551615, max: 18446744073709551615, step: 1)
    - direction ("ltr", "rtl")
    - img_composite (IMAGE, optional)
  - Outputs:
    - IMAGE
    - MASK
</details>

## Recent Changes

1. Add `alpha` and `background_alpha` to `🔧 Draw Text` node, let you can set the alpha of the text and the background.
2. Add more size options to `🔧 Empty Latent Size Picker` node, like 9:16, 3:4, 4:3, 16:9.

