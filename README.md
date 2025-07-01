# RandLA-Net
利用RandLA-Net实现室外点云数据语义分割
## 环境配置说明
本项目是在Linux环境下运行
### 安装
1.创建虚拟环境   
conda create -n randlanet python=3.6      
conda activate randlanet      
2.运行以下命令，在conda中安装Tf、CUDA和其他必要Python包      
pip install numpy==1.19.5 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install h5py~=3.1.0 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install cython==0.29.15 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install open3d-python==0.3.0 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install pandas==1.1.5 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install scipy==1.5.4 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install scikit-learn==0.21.3 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install PyYAML==6.0.1 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
pip install tensorflow-gpu==1.15 -i https://pypi.tuna.tsinghua.edu.cn/simple --timeout=120   
conda install cudatoolkit=11.2 cudnn=8.1 -c=conda-forge   
3.进入RandLA-Net目录  
cd utils/nearest_neighbors/   
python setup.py install --home="."   
cd ../../   
cd utils/cpp_wrappers/cpp_subsampling   
python setup.py build_ext --inplace   

本部分参考了https://zhuanlan.zhihu.com/p/670690151也有部分改动   


