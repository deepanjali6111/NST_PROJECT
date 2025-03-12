
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/deepanjali6111/NST_PROJECT/blob/main/Untitled1.ipynb)




Here's a concise **step-by-step README** for your Neural Style Transfer project:

---

# Neural Style Transfer Project  
*Apply artistic styles to images using TensorFlow and VGG19*  

##  Quick Start (Google Colab)  
1. **Open in Colab**
2. **Upload Images**:  
   - Content Image (e.g., portrait)  
   - Style Image (e.g., painting)  
3. **Adjust Parameters**: Use sliders for style/content balance  
4. **Click "Generate Style Transfer"**  

## 🔧 Implementation Steps  

### 1. Environment Setup  
```python
!pip install tensorflow numpy matplotlib ipywidgets --quiet
```

### 2. Image Preprocessing  
- **Load Images**: Resize to max 512px, normalize pixels [0,1]  
```python
def load_image(img_path, max_dim=512):
def deprocess_img(img):
```

### 3. VGG19 Model Setup  
- Extract features from 5 style layers + 1 content layer  
```python
content_layers = ['block5_conv2']
style_layers = ['block1_conv1', ..., 'block5_conv1']
def get_vgg_model():
```

### 4. Loss Calculations  
- **Content Loss**: Mean Squared Error (MSE)  
- **Style Loss**: Gram Matrix comparisons  
```python
def content_loss(...)
def gram_matrix(...)
def style_loss(...)
```

### 5. Training Loop  
1. Initialize generated image from content image  
2. For each epoch:  
   - Extract VGG19 features  
   - Calculate total loss (content + style)  
   - Apply Adam optimizer gradients  
   - Track best result  
```python
def style_transfer_training(...)
```

### 6. Interactive UI  
- File upload widgets for images  
- Sliders for parameters:  
  - `style_weight` (0.0001-0.1)  
  - `content_weight` (100-10,000)  
  - `epochs` (500-3000)  
```python
content_upload = FileUpload(...)
style_weight_slider = FloatSlider(...)
process_btn = Button(...)
```

## ⚙️ Parameters & Customization  
| Parameter          | Effect                          | Recommended Value |  
|--------------------|---------------------------------|-------------------|  
| **Style Weight**   | Artistic intensity              | 0.001-0.03        |  
| **Content Weight** | Original detail preservation    | 500-2000          |  
| **Epochs**         | Quality vs. speed tradeoff      | 1000-2000         |  

## 🛠️ Enhancements  
1. Add video support  
2. Implement Fast Style Transfer  
3. Deploy as web app  
4. Add multiple style blending  

---

**Key Features**:  
- Real-time progress visualization  
- Best result tracking during training  
- Interactive parameter controls  
- Noise reduction via TV loss  

**Technologies Used**:  
`TensorFlow` | `VGG19` | `NumPy` | `Matplotlib` | `ipywidgets`  


---


