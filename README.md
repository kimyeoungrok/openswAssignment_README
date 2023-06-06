# openswAssignment_README
오픈 소스 repo 설치 및 실행 방법
되도록이면 가상환경을 만들어 거기에 clone하는 것을 추천한다.
가상환경이 있는 위치에 다음 git명령어를 사용하여 clone해준다.
git clone https://github.com/chanubc/opensw23-KLKB

image01

CNN-Image-Colorization-Pytorch 폴더에 들어간다.
inference 폴더에 들어가 사용하고 싶은 이미지를 넣는다.
cmd창을 켜서 가상환경을 실행시킨 뒤에 inference_script.py 가 있는 위치로 이동한 뒤에 다음 명령어를 실행한다. inference_script.py --model_path models/saved_model.pth --image_path inference/[이미지 이름] cmd로 inference실행방법

inference

inference폴더로 이동하면 변환된 이미지 inference_output.jpg를 볼 수 있다.

output이미지
