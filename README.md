# SIA_MOT_Project

![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/8ab15bbd-e3c5-46e4-9b88-2f22428fda07)

# Project : Drone 영상 기반 다중 객체 추적


## 배경

드론 기술의 발전으로 드론들은 다양한 분야에서 사용되고 있으며, 드론이 촬영한 항공 영상은 고해상도와 넓은 시야를 제공합니다. 이러한 드론 영상을 활용하여 다중 객체 추적 기술을 개발하는 것은 중요한 응용 분야 중 하나입니다.

다중객체 추적, MOT(Multiple Object Tracking)은 이미지나 비디오에서 여러 객체(예: 차량, 보행자, 동물 등)의 움직임을 지속적으로 감지하고 추적하는 기술입니다. 이를 통해 도로 교통, 도시 계획, 자율 주행 차량, 보안 시스템, 환경 모니터링 등 다양한 분야에서 활용될 수 있습니다.

이 프로젝트는 교육기관 AIFFEL과 기업 SI Analytics의 기업 연계 프로젝트로
Drone영상(항공영상) 기반 다중 객체 추적을 목표로합니다.
드론으로 촬영한 비디오와 고해상도 이미지들로 이루어져 있는 Visdrone 데이터셋에서
차량과 사람의 위치를 식별하고 객체를 추적하는 것을 목표로 합니다.



## SI Analytics

SIA는 인공지능 기술을 통해 지구 관측의 자동화 및 분석의 융합을 이끌고 있습니다. 위성영상으로 지구를 관측하는 플랫폼이라는 방향성을 기반으로 GEOINT Solution을 주도합니다.

인공지능 기반 위성 영상 데이터셋 설계 구축 및 공급, 위성/항공영상 분석 및 인공지는 모델 설계, 지리공간 분석 솔루션 및 플랫폼 공급을 주요 사업으로 두고 있으며 Ovision, LabelEarth 같은 제품 및 서비스를 제공합니다.  위성/항공 영상을 통해  인공지능의 도움을 받아 여러 산업군이 빠르고 유기적으로 연결 될 수 있도록 협업하고 있습니다.

기업 SIA 에서는 위성/항공영상 분석 인공지능 모델 설계, 구축, 공급 및 지구관측 분석 솔루션 및 플랫폼을 제공합니다. Drone 기술의 발전에 따라 Drone 영상 정보를 이용한 관련시장의 성장과 산업이 확대되고 있으며, 연속되는 이미지로부터 관찰되는 Object의 위치를 찾고 추적하는 방법으로 연구가 다중객체 추적 연구가 진행되고 있습니다. 본 프로젝트에서는 기업 SIA와 연계하여 Airial view로 촬영된 드론영상 데이터(VisDrone)를 기반으로 Multiple Object Tracking(MOT)를 진행합니다.

## 프로젝트 기간
- 23.07.27 ~ 23.08.11

- ![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/ccf92cab-4a2e-4956-b1b8-76d9e884ace5)


## Colleagues
- [정혜원](https://github.com/heawonjeong)
    - 모델 검토 및 분석
    - 모델 실험
    - 논문 리딩
    - 깃 관리
- [이정진](https://github.com/jjlee6496)
    - 프로젝트 방향 설계
    - 데이터셋 분석 및 정제
    - 환경 설정
    - 모델 검토 및 분석
    - 모델 실험 및 시각화

- [주상현](https://github.com/SangHyun014)
    - 모델 검토 및 분석
    - 모델 실험 및 시각화


## Tools

### MMTracking

- Torch 1.13.0+cu116
- python 3.9.17
- cuda_11.5.r11.5
- miniconda conda 23.3.1
- mmcls 0.25.0
- mmcv-full 1.7.1
- mmdet 2.28.2
- mmtrack 0.14.0

### MMDetection

- Torch 1.10.0+cu111
- python 3.9.17
- cuda_11.5.r11.5
- miniconda conda 23.3.1
- mmengine 0.8.2
- mmcv 2.0.1
- mmdet 3.1.0
- mmpretain 1.0.0


## Datasets

**MOT17 데이터셋**

MOT19 데이터셋은 MOTChallenge를 위해 개발된 데이터셋으로, MOT를 위한 평가와 벤치마크를 위해 사용되는 데이터셋입니다. MOT19 데이터셋의 annotation 정보는 COCO format으로 되어있는데 이는 bounding box의 좌상단 좌표와 너비와 높이와 더불어, occlusion 여부, truncation 여부 등을 포함하고 있습니다.

**COCO Format**
MOT COCO format은 COCO 형식의 기본 구조를 따르면서도 객체 추적 관련 정보를 추가로 포함하여 다중 객체 추적 문제를 다루는 데 특화된 형식입니다. 이를 통해 알고리즘은 객체의 식별, 이동 및 속성 변화를 정확하게 추적할 수 있는 능력을 평가하고 비교할 수 있습니다.

카테고리 id를 포함해서 bounding box의 위치 및 넓이 등을 포함하고 있습니다.

COCO foramt의 예시는 다음과 같습니다.

```python
{"category_id": 1,
 "bbox": [374.0, 305.0, 33.0, 89.0], "area": 2937.0,
"iscrowd": false,
"visibility": 0.25,
"mot_instance_id": 0, "mot_conf": 1.0, "mot_class_id": 1,
"id": 75814, "image_id": 3515, "instance_id": 0}

```

**Visdrone 데이터**

[VIsDrone](https://github.com/VisDrone/VisDrone-Dataset)

Visdrone  데이터는 vision 기반 UAV(Unmanned Aerial Vehicle)로 촬영한 비디오 데이터셋으로, 객체 감지와 추적을 위해 만들어진 대규모 데이터셋입니다.  도시, 시골, 공원 등 다양한 장소와 날씨 및 밝기 조건과 더불어 많은 객체가 밀집되어있거나 물체에 가려진 다양한 상황에서 수집되었습니다. 객체는 자동차, 보행자, 자전거와 같은 11개의 다양한 클래스로 분류되고, 260만개 이상의 ground-truth bounding box와 annotation 정보를 포함하고 있습니다. annotatino 정보에는 객체 클래스와 bounding box 위치와 크기 정보 이외에도 occlusion 정도, truncation 유뮤와 같은 중요한 속성도 제공됩니다.


**Annotation**

- frame_index: 비디오 프레임의 인덱스로 1부터 시작합니다.
- target_id: 다른 프레임들 사이에 bounding boxes의 시간적인 대응 관계를 보기 위해 사용합니다
- bbox: x,y,w,h 좌상단 x,y 좌표와 넓이, 높이
- score: confidence score
- Object Category
    
    ```
    Classes in VisDrone:
    0: 'ignored regions' - 무시할 영역, 주로 일정범위 떨어져 있는 구역에 표시가 되어 있음
    1: 'pedestrian' - 보행자, 움직임이 있는 사람들
    2: 'people' - 정적인 사람들. 주로 탈것에 앉아있거나 바닥에 앉아있는것 처럼 움직임이 없다
    3: 'bicycle'
    4: 'car'
    5: 'van'
    6: 'truck'
    7: 'tricycle'
    8: 'awning-tricycle'
    9: 'bus'
    10: 'motor',
    11: 'others'
    ```

    아래 그림과 같이 Category가 0인 Object는 confidence score가 0입니다.
  ![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/29308b11-012d-4c08-8873-f93f7b874bba)

  - truncation: Object의 Truncation 여부(0 or 1). Object 전체가 프레임 내에 완전히 존재하면 Truncation이 일어나지 않은 것이고, Object가 프레임 밖으로 잘리면 Truncation이 발생한 것입니다. 빨간색 Bounding Box는 Truncation이 1, 초록색 Boudning Box는 0입니다. 
    ![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/09019b19-aa7f-4c26-bfda-f430c16ec3b7)

    - occlusion: Object가 다른 물체 혹은 다른Object에 가려졌을 때 Occlusion이 발생했다고 하며 그 정도에 따라 0, 1, 2 로 점수를 매깁니다.
      ![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/7261f393-a9a2-4f63-a99c-7aa388cb1935)


**데이터 정제**
- 자전거, motor 종류는 주로 사람과 분리된 Object 2개로 인식하지만 크기가 작아지면 사람과 vehicle이 합쳐져 Object 1개로 인식하는 현상이 발생합니다. 따라서 pedestrian, car, van, bus, truck 5가지 class 로 정제하여 사용하였습니다.

**Insight**

- 아래 그림과 같이 드론의 rotation으로 인해 화면이 흐려지며 한 프레임 내에 Object가 존재하지 않는 경우가 발생합니다. 이와 같이 드론의 극적인 움직임에 따른 시점 변화 문제로 인해 train의 어려움을 겪을 것으로 예상하여 strong Augmentation을 적용하여 실험을 계획하였습니다.
- truncation 값이 0인 Object를 학습에서 제외하여 프레임 내 Objet 전체가 있는 data들로만 학습을 진행한다면 Object에 대한 더 정확한 학습과 드론 시점의 중앙에 더욱 집중할 수 있다고 예상하였습니다.

  따라서 truncation 유무와 augmentation(no aug, mixup, mosaic, mixup mosaic)별로 모델 당 총 8개의 실험을 계획하였습니다. 
![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/8a8c2335-272d-41eb-ad3e-a215be87b2e2)


## Model 선정

**MOT 방식 선정**
- TBD(Tracking By Detection)

먼저 객체 감지 모델(Detection model)을 사용하여 각 프레임 이미지에서의 객체를 먼저 detect 한 후 이 정보를 바탕으로 tracking을 진행하는 방식입니다.

TBD는 다른 tracking 방식보다 Detection 정보를 기반하므로, 객체 검출에 있어서의 정확도가 더 높습니다. 따라서 TBD 방식을 사용했을 때 더 높은 정확도를 보장합니다.

1) Object Detection

2) Data Association

3) Tracklet Generation & Update

그리고 저희 프로젝트에서는 car, pedestrian, van, truck, bus 총 5개의 class에 대한 검출을 시행합니다. 이렇게 여러가지 클래스를 감지할 때 TBD 방식이 더 효과적으로 작동합니다. 

또한 TBD 방식을  사용하며 이제까지 개발된 다양한 Detector 모델과 Tracker 모델을 유연하게 결합하여 사용할 수 있습니다. 

마지막으로 TBD는 빠른 프레임 속도로 객체를 추적하는데 효과적이므로, 실시간 객체 추적에 용이합니다. 

- Detector 선택

detector는 1-stage model과 2-stage model로 나눌 수 있습니다. 2-stage detector는 region proposal과 classification이 순차적으로 이루어집니다. 즉, Localization과 Classification 이 순차적으로 이루어집니다. 이와 다르게 1-stage 모델은 위 두 과정이 동시에 이루어집니다. 2-stage model은 더 높은 정확도를 보이지만, 1-stage model보다 더 시간이 오래 걸립니다. 저희는 좀 더 나은  FPS 성능을 얻어내기 위해 1-stage detector를 선정하였습니다. 

1. RetinaNet
![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/a501c66e-a943-487c-9ead-e75f671e7230)
데이터의 각 프레임 내에 Object 가 있는 영역인지 아닌지에 따라(IoU Threshold) positive/negative sample로 구분합니다. 일반적으로 이미지 내의 어려운 양성 샘플(객체영역)보다 쉬운(배경영역)이 압도적으로 많으므로 class imbalance 문제가 발생합니다. Retinanet에서는 새로운  loss function인 focal loss 를 제시하여 class imbalance 문제를 해결하여 모델의 정확도를 높입니다.

![image](https://github.com/heawonjeong/SIA_MOT_Project/assets/126838460/e3bcfbc5-1865-42f8-aa10-edead04a3384)

2. YOLOX




