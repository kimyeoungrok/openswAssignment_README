## Installation
실행 조건 : pc에 NVIDIA기종의 그래픽카드가 설치되어있어야 한다.  
<오픈 소스 repo 설치 및 실행 방법>  
되도록이면 가상환경을 만들어 거기에 clone하는 것을 추천한다.  
<가상환경 구축방법>
![가상환경생성](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/20e937b6-f2d4-4a6d-9df1-5458c354219f)  
cmd창을 연뒤에 가상환경을 생성하고 싶은 파일 위치로 이동해서 다음과 같은 명령어를 입력해준다.  
virtualenv opensw   
(opensw는 가상환경이름이다. 필요하다만 다른 이름을 지정해서 사용해도 무관하다.)  
그런 뒤에 opensw\Scripts\activate 명령어를 입력해주어서 가상환경을 실행해준다.  

<개발환경 구축>  
위 레포지토리를 실행하려면 cuda, torch, torchvision등 여러 모듈들의 설치가 필요하다.  
<cuda설치>  
shift + ctrl + esc 버튼을 눌러 작업 관리자를 실행한 후 성능 탭에 접속  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/ff93a7e6-182e-4670-b55e-91c0e2853d70)  
GPU메뉴에 접근하여 내 pc가 어떤 그래픽 카드를 쓰고 있는지 확인  
(필자는 NVIDIA GeForce GTX 1060을 쓰고 있음을 알 수 있다.)  
<NVIDIA Driver 사이트 접속>  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/c5530677-0496-4e66-8e5a-94799e1c0afd)  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/6fa65bcf-eff9-4342-83ee-63a14331db3f)  
아까 작업관리자에서 확인했던 그래픽 카드 정보를 바탕으로 해당 product Series와 Product를 선택한 뒤에 Search를 누르고 Driver를 다운/설치를 한다.  
  
<적절한 CUDA버전 확인>  
cmd창을 열어서  
cd C:\Program Files\NVIDIA Corporation\NVSMI 명령어를 실행한 뒤에  
nvidia-smi.exe 명령어 실행  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/ed80560e-9095-4712-88d7-ba2652a16df9)  
그러면 다음과 같은 표를 얻을 수 있고 우측 상단에 CUDA Version을 확인할 수 있다.  
(필자의 경우엔 10.2라고 나온다.)  
위 버전을 잘 기억해 두자  
  
<CUDA toolkit설치>  
  
https://developer.nvidia.com/cuda-toolkit-archive  
다음 사이트에 접속하여 표에서 얻은 CUDA Version과 같은 것을 다운 받는다,  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/1eead272-d0b6-483f-a85a-a9ff89aa8d9c)  

이제 다시 cmd창을 활용하여 아까 생성했던 가상환경을 돌아가준다.  
  
<라이브러리 설치>  
https://pytorch.org/get-started/previous-versions/  
위 사이트를 참고 하여 본인 CUDA버전과 맞는 pytorch, torchvision, torchaudio 라이브러리를 설치한다.  
![파이토치 설치](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/a7f5dcc0-2a4a-41a6-be74-dd162809b322)  
  
![토치cuda호환](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/1d4f1fc9-c022-49fb-a15a-d7695123cfe1)  
위와 같이 명령어를 입력하여 설치한 토치와 cuda가 호환이 되는지 확인한다.  
사진과 같이 True가 뜨면 정상적으로 실행된다는 뜻이다.  
False가 뜨면 쿠다 버전과 호환이 되는 다른 토치버전을 설치하거나 cuda toolkit을 재설치하는걸 권장한다.  
  
다음은 Matplotlib이랑 scikit-image 그리고 CV2라이브러리를 다운/설치 한다.  
Matplotlib설치 명령어  
![mat설치](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/4a102dbc-4252-474b-a4e0-0dcb336fd1b4)  
pip install matplotlib  
  
scikit-image설치 명령어  
![사이킷](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/84407eef-9d55-4399-aa02-889cbb943374)  
pip install scikit-image  
  
CV2설치 명령어  
![cv2](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/097fbe2c-9c5e-455f-8ba4-077b9f9729bb)  
pip install opencv-python  
  
<clone및 실행방법>  
가상환경이 있는 위치에 다음 git명령어를 사용하여 clone해준다.  
git clone https://github.com/chanubc/opensw23-KLKB  
![image01](https://github.com/chanubc/opensw23-KLKB/assets/106955456/43be217b-19f9-4025-ab66-776f5452950a)  
CNN-Image-Colorization-Pytorch 폴더에 들어간다.  
inference 폴더에 들어가 사용하고 싶은 이미지를 넣는다.  
cmd창을 켜서 가상환경을 실행시킨 뒤에 inference_script.py 가 있는 위치로 이동한 뒤에 다음 명령어를 실행한다.
inference_script.py --model_path models/saved_model.pth --image_path inference/[이미지 이름]
![cmd로 inference실행방법](https://github.com/chanubc/opensw23-KLKB/assets/127182406/7354c0ca-4625-4b63-b0c6-41447066366f)  


![inference](https://github.com/chanubc/opensw23-KLKB/assets/127182406/179b974e-c4c9-4055-976a-3a4643f463ef)  

inference폴더로 이동하면 변환된 이미지 inference_output.jpg를 볼 수 있다.

![output이미지](https://github.com/chanubc/opensw23-KLKB/assets/127182406/05a98fc3-e1de-4ab6-8dec-45b618f1b831)  
  
## Analysis  
위 모델이 어떤 이미지들을 잘 colorization시키는지 분석해 보았다.

<분석방법>
1. 크기가 256*256인 원본 이미지를 준비한다.  
2. 원본 이미지를 colorization시킨다.  
3. colorization시킨 이미지와 원본 이미지의 각 픽셀간 RGB거리를 구한다.  
4. 그렇게 구한 RGB거리들을 모두 더해준다.  
5. 결과값을 이미지 카테고리별로 묶어서 서로 평균을 내어 이미지 카테고리별로 어떤 차이가 있는지 확인한다. (RGB거리가 짧을 수록 원본이미지와의 색상 차이가 없다는 것을 의미합니다.)  
  
분석방법이 이해가 잘 안되는 분도 있을 수 있어서 쉽게 예를 들어 보겠습니다.  
만약 크기가 2*2인 원본이미지와 그 이미지를 Colorization시킨 이미지가 있을 때 이 이미지들의 RGB거리 값은 다음과 같이 구합니다.  
  
![RGB거리예시](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/89beab22-3b2c-48c7-87e9-77d530836dd9)  

분석하는데 사용한 이미지들은 다음과 같습니다.  

건물사진 55장 (인터넷에서 구한 건물사진 25장 + 저희가 찍은 사진 30장)  
인물사진 55장 (인터넷에서 구한 인물사진 55장)  
자연물사진 55장 (인터넷에서 구한 자연물 사진 25장 + 저희가 찍은 사진 30장)

이미지 카테고리별로 RGB거리의 평균값을 구해보았습니다.    
  
![카테고리별 평균 거리](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/920ef42a-83b1-4700-a0eb-ebf06bda72d9)  
  
차이를 눈에 잘 보이게 하기 위해 그래프로 나타내보았습니다.  
![카테고리별 평균 거리(그래프)](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/4ea4e25b-eaf4-4bff-b1c8-db7e698808bb)  
  
분석 결과 위 모델은 건물이미지를 다른 이미지보다 colorization을 잘 시키는데 반해, 인물이미지는 다른 이미지들보다 colorization을 잘 못시키고 있음을 알 수 있습니다.  
  
이번에는 분석한 카테고리별 이미지들을 다 합쳐서 RGB거리가 긴 이미지 10개, RGB거리가 짧은 이미지 10개를 뽑아보겠습니다.  
  
먼저 RGB거리가 짧은 이미지10개 즉 colorization이 다른 이미지에 비해 잘된 이미지들을 선정해보았습니다.
  
![image](https://github.com/kimyeoungrok/openswAssignment_README/assets/127182406/3d633952-afc7-4f81-ab5c-64621c82a7a6)  



