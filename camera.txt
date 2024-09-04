import cv2

# 웹캠 캡처 객체 생성
cap = cv2.VideoCapture(0)

while True:
    # 프레임 1개 읽기
    ret, frame = cap.read()

    # 프레임이 제대로 읽혔는지 확인
    if not ret:
        print("프레임을 가져올수 없습니다.!!!")
        break

    # 프레임을 화면에 표시
    cv2.imshow('Webcam', frame)

    # 키 입력 및 탈출키 정의  'q'이면 탈출
    if cv2.waitKey(1) & 0xff == ord('q'):
        break

# 종료를 위한 자원 해제
cap.release()
cv2.destroyAllWindows()


        
