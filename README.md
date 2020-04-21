# retinanet

# Installation

1. Clone this repository.

2. Ensure numpy is installed using pip install numpy --user

3. In the repository, execute pip install . --user. Note that due to inconsistencies with how tensorflow should be installed, this package does not define a dependency on tensorflow as it will try to install that (which at least on Arch Linux results in an incorrect installation). Please make sure tensorflow is installed as per your systems requirements.

4. Alternatively, you can run the code directly from the cloned repository, however you need to run python setup.py build_ext --inplace to compile Cython code first.

5. Optionally, install pycocotools if you want to train / test on the MS COCO dataset by running pip install --user git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI.

# creating or preprocess for your custom dataset:

1. initially you have to create 2 csv files.

2. 1st csv files contain the no of classes involved in training.

3. 2nd csv files contains name of the image file,location of object in image i.e coordinates of box,class name.

4. After creating 2 csv files place it in the downloaded keras-retinanet-master repository (i.e the main folder that you have extracted and unziped from github)

5. copy all the image that you want to train in the main folder i.e keras-retinanet-master repository.

# How to start traininig?


In the terminal you need to type "pyhton keras_retinanet/bin/train.py csv /path/to/csv/file/containing/annotations.csv /path/to/csv/file/containing/classes.csv"

# parametrs that you can adjust and try during training:

1) epochs: usually default is 50 epochs ,you can change it according to your requirment.example:pyhton keras_retinanet/bin/train.py --epochs 250 csv /path/to/csv/file/containing/annotations.csv /path/to/csv/file/containing/classes.csv(note:remember to set epochs after train.py and before csv,all the parameters that i am gonna mention below should place in same location after train.py and before csv)

2) '--snapshot':'Resume training from a snapshot.'

3) '--imagenet-weights', help='Initialize the model with pretrained imagenet weights. This is the default behaviour.', action='store_const', const=True, default=True

4) '--weights', help='Initialize the model with weights from a file.' group.add_argument('--no-weights', help='Don't initialize the model with any weights.', dest='imagenet_weights', action='store_const', const=False)

5) '--backbone', help='Backbone model used by retinanet.', default='resnet50', type=str

6) '--batch-size', help='Size of the batches.', default=1, type=int

7) '--gpu', help='Id of the GPU to use (as reported by nvidia-smi).'

8) '--multi-gpu', help='Number of GPUs to use for parallel processing.', type=int, default=0

9) '--multi-gpu-force', help='Extra flag needed to enable (experimental) multi-gpu support.', action='store_true'

10) '--epochs', help='Number of epochs to train.', type=int, default=50

11) '--steps', help='Number of steps per epoch.', type=int, default=10000

12) '--lr', help='Learning rate.', type=float, default=1e-5

13) '--snapshot-path', help='Path to store snapshots of models during training (defaults to './snapshots')', default='./snapshots'

14) '--tensorboard-dir', help='Log directory for Tensorboard output', default='./logs'

15) '--no-snapshots', help='Disable saving snapshots.', dest='snapshots', action='store_false'

16) '--no-evaluation', help='Disable per epoch evaluation.', dest='evaluation', action='store_false'

17) '--freeze-backbone', help='Freeze training of backbone layers.', action='store_true'

18) '--random-transform', help='Randomly transform image and annotations.', action='store_true'

19) '--image-min-side', help='Rescale the image so the smallest side is min_side.', type=int, default=800

20) '--image-max-side', help='Rescale the image if the largest side is larger than max_side.', type=int, default=1333

21) '--config', help='Path to a configuration parameters .ini file.'

22) '--weighted-average', help='Compute the mAP using the weighted average of precisions among classes.', action='store_true')

23) '--compute-val-loss', help='Compute validation loss during training', dest='compute_val_loss', action='store_true'

#Fit generator arguments

24) '--multiprocessing', help='Use multiprocessing in fit_generator.', action='store_true'

25) '--workers', help='Number of generator workers.', type=int, default=1

26) '--max-queue-size', help='Queue length for multipnerator.', type=int, default=10)




