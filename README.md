##옷 추천 인공지능 프로그램

1. 옷을 잘입지 못하는 사람들을 위한 **옷 추천**을 할 것이다.
2. 머신러닝을 이용해 사용자의 신체비율과 길이를 카메라로 측정하여, 비슷한 신체의 연예인이나 모델을 보여주고 이에 맞는 옷들을 추천해준다.
3. 이 프로그램으로 인해 옷을 잘입고 싶었지만 센스가 부족해 그럴 수 없었던 사람들이 잘입는 디딤돌이 될 것이다.
4. 'import cv2
import numpy as np
import pyopenpose as op

# OpenPose 초기화
params = dict()
params["model_folder"] = "./models/"

# OpenPose의 Wrapper 초기화
opWrapper = op.WrapperPython()
opWrapper.configure(params)
opWrapper.start()

# 영상 또는 이미지 파일 불러오기
image_path = "person.jpg"
image = cv2.imread(image_path)

# OpenPose로 이미지 처리
datum = op.Datum()
datum.cvInputData = image
opWrapper.emplaceAndPop([datum])

# 처리된 이미지와 keypoints 출력
print("Pose keypoints: \n", datum.poseKeypoints)
cv2.imshow("OpenPose Output", datum.cvOutputData)
cv2.waitKey(0)
cv2.destroyAllWindows()'
[깃허브 openpose]([https://example.com](https://github.com/CMU-Perceptual-Computing-Lab/openpose))



