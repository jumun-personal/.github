# 물류 이커머스 시스템 (백엔드 4인)
- 소개: 개인용으로 fork된 organization입니다.
- 프로젝트 목표: 대규모 트래픽에 견고한 시스템을 설계

## 역할

### 허브, 재고 서비스 담당 
Repository: [hub-product-stock-company](https://github.com/jumun-personal/hub-product-stock-company)
  - 재고 관리 기능
  - 허브 관리 기능
### 개인 고도화 
  - **주문 대기열 트래픽 제어**
    - 대기열 [QueueServiceImpl.java](https://github.com/jumun-personal/wait-room/blob/main/src/main/java/com/jumunhasyeo/ratelimiter/queue/service/QueueServiceImpl.java)
  - **주문 API 최적화 평균 응답 시간 약 32% 개선**
    - [BlackFridayOrderOrchestrator.class](https://github.com/jumun-personal/order-to-shipping-service/blob/dev/src/main/java/com/jumunhasyeotjo/order_to_shipping/order/blackfriday/applicatiion/BFOrderOrchestrator.java)

### 인프라
- **GithubAction ECS CI/CD 구현**
  - [.github/workflow/**](https://github.com/jumun-personal/hub-product-stock-company/tree/dev/.github/workflows)
- **AWS 인프라 구축(ECS 구성 및 배포 담당)**
