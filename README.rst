PyTorch-SyncBatchNorm
=====================
created by `Hang Zhang <http://hangzh.com/>`_

[`Link to MXNet Gluon Implementation <https://github.com/zhanghang1989/MXNet-Gluon-SyncBN/>`_] 

Synchronized Batch Normalization (SyncBN) [1]_ . We follow the sync-onece implmentation described in the paper [2]_ . If you are not familiar with Synchronized Batch Normalization, please see this `blog <http://hangzh.com/blog/SynchronizeBN/>`_. 

Jump to:

- `How to use SyncBN`_
- `MNIST example <https://github.com/zhanghang1989/PyTorch-SyncBatchNorm/blob/master/mnist.ipynb>`_

Install PyTorch and Encoding Package from Source
------------------------------------------------

* Install PyTorch from Source (recommended). Please follow the `PyTorch instructions <https://github.com/pytorch/pytorch#from-source>`_.

* Install `Encoding package <http://hangzh.com/PyTorch-Encoding/index.html>`_ :

  - Clone the repo
  
  .. code::

    git clone https://github.com/zhanghang1989/PyTorch-Encoding && cd PyTorch-Encoding

  - On Linux::

  .. code::
  
    pip install -r requirements.txt
    python setup.py install

  - On Mac OSX::

  .. code::
  
    pip install -r requirements.txt
    MACOSX_DEPLOYMENT_TARGET=10.9 CC=clang CXX=clang++ python setup.py install

How to use SyncBN
-----------------

``from encooding.nn import BatchNorm2d``, everything else looks the same as before.


MNIST Example
-------------

Please visit the `python notebook <https://github.com/zhanghang1989/PyTorch-SyncBatchNorm/blob/master/mnist.ipynb>`_

See `mnist.py <https://github.com/zhanghang1989/PyTorch-SyncBatchNorm/blob/master/mnist.py>`_, run the experiments::
  
  CUDA_VISIBLE_DEVICES=0,1,2,3 python tests/mnist.py

Reference
---------

.. [1] Ioffe, Sergey, and Christian Szegedy. "Batch normalization: Accelerating deep network training by reducing internal covariate shift." *ICML 2015*

.. [2] Hang Zhang, Kristin Dana, Jianping Shi, Zhongyue Zhang, Xiaogang Wang, Ambrish Tyagi, and Amit Agrawal. "Context Encoding for Semantic Segmentation." *CVPR 2018*
