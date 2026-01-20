# 물류 이커머스 시스템 (3개월 / 백엔드 4인)
- 소개: 개인용으로 fork된 organization입니다.
- 프로젝트 목표: 대규모 트래픽에 견고한 시스템을 설계

## 역할

### 허브, 재고 서비스 담당 
Repository: [hub-product-stock-company](https://github.com/jumun-personal/hub-product-stock-company)
  - **DB update row lock 을 이용해 재고 차감 처리량 24% 향상** [StockVariationServiceImpl](java/com/jumunhasyeo/stock/application/StockVariationServiceImpl.java)
     <img width="2764" height="368" alt="image" src="https://github.com/user-attachments/assets/4fc06761-040b-4cc0-9c1d-72e958429f47" />

  - **전국 허브 정보를 Redis에서 로컬 캐시로 전환하여 응답시간 33% 향상** [HubCaffeineCachedDecoratorService](https://github.com/jumun-personal/hub-product-stock-company/blob/dev/src/main/java/com/jumunhasyeo/hub/hub/application/HubCaffeineCachedDecoratorService.java)
     <img width="2764" height="1136" alt="image" src="https://github.com/user-attachments/assets/436778d1-ef2f-4a2c-829a-25e74fc97ada" />

### 개인 고도화 
  - **트래픽 제어 ratelimit**
    - 전체 요청 처리율 제한 + 대기열 [GlobalQueueService.java](https://github.com/jumun-personal/rate-limiter-proxy/blob/main/src/main/java/com/jumunhasyeo/ratelimiter/service/global/GlobalQueueService.java)
    - PG 처리율 제한 + 대기열 [pg/RateLimiterService.java](https://github.com/jumun-personal/rate-limiter-proxy/blob/main/src/main/java/com/jumunhasyeo/ratelimiter/service/pg/RateLimiterService.java)
  - **주문 API 최적화 평균 응답 시간 약 32% 개선**
    - [BlackFridayOrderOrchestrator.class](https://github.com/jumun-personal/order-to-shipping-service/blob/dev/src/main/java/com/jumunhasyeotjo/order_to_shipping/order/blackfriday/applicatiion/BFOrderOrchestrator.java)

### 인프라
- **GithubAction ECS CI/CD 구현**
  - [.github/workflow/**](https://github.com/jumun-personal/hub-product-stock-company/tree/dev/.github/workflows)
- **AWS 인프라 구축**

