# boostcamp_pstage10

# Environment
## 1. Docker
```bash
docker run -it --gpus all --ipc=host -v ${path_to_code}:/opt/ml/code -v ${path_to_dataset}:/opt/ml/data placidus36/pstage4_lightweight:v0.4 /bin/bash
```
## 2. Install dependencies
```
pip install -r requirements.txt
```

# Run
## 1. train
python train.py --model ${path_to_model_config} --data ${path_to_data_config}
# Ex) python train.py --model configs/model/mobilenetv3.yaml --data configs/data/taco.yaml

## 2. inference(submission.csv)
python inference.py --model_dir ${저장된 모델 root 경로} --weight_name ${모델 weight 이름} --img_root ${test 데이터 경로}
# EX) python inference.py --model_dir /opt/ml/code/exp/latest --weight best.pt --img_root /opt/ml/data/test/

# Reference
Our basic structure is based on [Kindle](https://github.com/JeiKeiLim/kindle)(by [JeiKeiLim](https://github.com/JeiKeiLim))
