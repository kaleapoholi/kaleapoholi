### How to use the code : 
 
DATASET : You should have two folders inside: `train` and `valid` as well as a bunch of csv files.

To run the script you can execute it with the following arguments:
```
def parse_arguments():
    parser = argparse.ArgumentParser()
    parser.add_argument('-t', '--task', type=str, required=True,
                        choices=['abnormal', 'acl', 'meniscus'])
    parser.add_argument('-p', '--plane', type=str, required=True,
                        choices=['sagittal', 'coronal', 'axial'])
    parser.add_argument('-w', '--datafolder', type=str, default='../data')
    parser.add_argument('-s', '--suffixe', type=str, required=True)
    parser.add_argument('--epochs', type=int, default=50)
    parser.add_argument('--gpu', type=int, default=0)
    parser.add_argument('--lr', type=float, default=1e-4)
    parser.add_argument('--momentum', type=float, default=0.9)
    args = parser.parse_args()
    return args
```

example to train a model to detect meniscus tears on the coronal plane for a 50 epochs:

`python train_mrnet.py -t meniscus -p coronal --epochs=50 --suffixe my_training1`

