
# Change mirror
		
```

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch
````

### Step 2: Create a New Anaconda Environment[](https://saturncloud.io/blog/how-to-install-opencv-package-with-anaconda-a-guide-for-data-scientists/#step-2-create-a-new-anaconda-environment)

Creating a new environment for your OpenCV project is a good practice. It helps isolate your project and its dependencies from other Python projects. Use the following command to create a new environment:


```bash
conda create -n opencv_env python=3.8

```



### Step 3: Activate the Environment[](https://saturncloud.io/blog/how-to-install-opencv-package-with-anaconda-a-guide-for-data-scientists/#step-3-activate-the-environment)

Before installing OpenCV, you need to activate the environment you just created. Use the following command:

```bash
conda activate opencv_env
```



### Step 4: Install OpenCV [](https://saturncloud.io/blog/how-to-install-opencv-package-with-anaconda-a-guide-for-data-scientists/#step-4-install-opencv)

Now, you’re ready to install OpenCV. Use the following command:

```bash
conda install -c conda-forge opencv
```

## Install using requirement.txt



**使用 requirements.txt 安装包**：

在激活的环境中，使用以下命令安装 `requirements.txt` 文件中列出的所有包：

Copy code

`pip install -r requirements.txt`