## 1.OBI-Designer

### 1.1 Flowchart of WordArt generation

1. Character glyph design: As a pictographic script, oracle bone script has a complex structure, many strokes and a single character has a complete meaning. If the entire character is deformed, the deformed character will be unrecognizable. Therefore, **part of the character is used as the deformation object**.
1. Diffusion model (SD) and DDIM inversion are used to perform interval score matching to match the text contour with the prompt semantics.

![pipline](asset\pipline.png)

### 1.2 Environment Configuration（Ubuntu 20.04）

1. Create a conda virtual environment and install the toolkit

   ```sh
   conda create --name word python=3.8.15
   conda activate word
   pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 --extra-index-url https://download.pytorch.org/whl/cu113
   conda install -y numpy scikit-image
   conda install -y -c anaconda cmake
   conda install -y -c conda-forge ffmpeg
   pip install svgwrite svgpathtools cssutils numba torch-tools scikit-fmm easydict visdom freetype-py shapely
   pip install opencv-python==4.5.4.60  
   pip install kornia==0.6.8
   pip install shapely
   ```

2. Install the diffusers library (**Library you must know to use the diffusion model**)

   ```sh
   pip install diffusers
   pip install transformers scipy ftfy accelerate
   ```

   

3. Install the diffvg library (**Install under Linux environment, Windows needs to configure the C++ development environment, which is too troublesome**)

   ```sh
   git clone https://github.com/BachiLi/diffvg.git
   cd diffvg
   git submodule update --init --recursive
   python setup.py install
   ```

4. Pre-trained weights: Link:https://pan.baidu.com/s/1tZVC8xtrSYkiNSJmAFElYw  Extraction code：8tza 

## 2.Test Results

### 2.1 Dataset

The experiment takes the Hanyi Chen-style oracle bone script[^1] developed jointly by Professor Chen Nan of Tsinghua University and the Hanyi character library as an example.

[^1]:[汉仪陈体甲骨文-汉仪字库 (hanyi.com.cn)](https://www.hanyi.com.cn/productdetail.php?id=2638)

### 2.2 Creative oracle bone script of Chinese zodiac

The 1st and 2nd rows in the picture are oracle bone characters, the 2nd and 3rd rows are characters after the shape has been changed, and the 4th and 5th rows are characters after adding texture.

![example](asset\example.png)
