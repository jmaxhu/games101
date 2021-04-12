# 作业1

该作业主要是验证编译环境是否安装正确以及Eigen库的基本使用。其中用到了[向量、矩阵](https://eigen.tuxfamily.org/dox/group__TutorialMatrixArithmetic.html)的使用。

## 向量

向量定义

```c++
Eigen::Vector3f v(1.0f, 2.0f, 3.0f);
Eigen::Vector3f w(1.0f, 0.0f, 0.0f);
```

向量运算

```c++
Eigen::Vector3f v1 = v + w;
Eigen::Vector3f v2 = v * 3.0f;
```

## 矩阵

矩阵定义

```c++
Eigen::Matrix3f i, j;
i << 1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0;
j << 2.0, 3.0, 1.0, 4.0, 6.0, 5.0, 9.0, 7.0, 8.0;
```

矩阵运算

```c++
Eigen::Matrix3f m1 = i + j;
Eigen::Matrix3f m2 = i * 2.0f;
Eigen::Matrix3f m3 = i * j;
```

## 作业
给定一个点 P =(2,1), 将该点绕原点先逆时针旋转 45◦，再平移 (1,2), 计算出 变换后点的坐标(要求用齐次坐标进行计算)。

```c++
std::cout << "begin homework" << std::endl;
Eigen::Vector3d p(2.0, 1.0, 1.0);
Eigen::Matrix3d r;
Eigen::Matrix3d t;
double deg = 45.0 / 180.0 * M_PI;
r << cos(deg), -1.0 * sin(deg), 0,
      sin(deg), cos(deg), 0,
      0, 0, 1;
t << 1, 0, 1,
      0, 1, 2,
      0, 0, 1;
p = t * r * p;

std::cout << "After rotation and transform the point is at:" << p[0] << "," << p[1] << std::endl; 
```

题目要求用齐次坐标。 矢量的旋转和平移都可以通过矩阵运算完成。

旋转矩阵为：[(cos(deg), -sin(deg), 0), (sin(deg), cos(deg), 0), (0, 0, 1)]

平移矩阵为：[(1, 0, 1), (0, 1, 2), (0, 0, 1)] // 平移(1, 2)

最终的结果可以通过矩阵相乘再乘矢量的方式完成。矩阵虽然不符合交换律，但符合结合律。

## 程序运行

```c++
mkdir build
cd build
cmake ..
make
./Transformation
```