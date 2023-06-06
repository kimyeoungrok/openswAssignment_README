## Installation
오픈 소스 repo 설치 및 실행 방법  
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


가상환경이 있는 위치에 다음 git명령어를 사용하여 clone해준다.  
git clone https://github.com/chanubc/opensw23-KLKB  
![image01](https://github.com/chanubc/opensw23-KLKB/assets/106955456/43be217b-19f9-4025-ab66-776f5452950a)  
GPU메뉴에 접근하여 내 pc가 어떤 그래픽 카드를 쓰고 있는지 확인  
(필자는 NVIDIA GeForce GTX 1060을 쓰고 있음을 알 수 있다.)  
CNN-Image-Colorization-Pytorch 폴더에 들어간다.  
inference 폴더에 들어가 사용하고 싶은 이미지를 넣는다.  
cmd창을 켜서 가상환경을 실행시킨 뒤에 inference_script.py 가 있는 위치로 이동한 뒤에 다음 명령어를 실행한다.
inference_script.py --model_path models/saved_model.pth --image_path inference/[이미지 이름]
![cmd로 inference실행방법](https://github.com/chanubc/opensw23-KLKB/assets/127182406/7354c0ca-4625-4b63-b0c6-41447066366f)  


![inference](https://github.com/chanubc/opensw23-KLKB/assets/127182406/179b974e-c4c9-4055-976a-3a4643f463ef)  

inference폴더로 이동하면 변환된 이미지 inference_output.jpg를 볼 수 있다.

![output이미지](https://github.com/chanubc/opensw23-KLKB/assets/127182406/05a98fc3-e1de-4ab6-8dec-45b618f1b831)  
