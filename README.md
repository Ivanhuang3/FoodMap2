FoodMAP2 專案架構 🍽️
專案概述 📖
FoodMAP2 是一個基於 Spring Boot 的美食地圖應用程式，提供餐廳搜尋、評論和用戶管理功能，旨在為用戶打造個人化的美食探索體驗。
技術棧 ⚙️

後端框架: Spring Boot 3.2.3
資料庫: H2 (開發環境)
安全框架: Spring Security + JWT
模板引擎: Thymeleaf
緩存: Caffeine
建構工具: Maven
Java版本: 17

專案結構 📂
src/main/java/com/foodmap2/
├── auth/                           # 🔐 認證模組
│   ├── controller/                 # 認證控制器
│   ├── service/                    # 認證服務
│   ├── dto/                        # 認證相關DTO
│   └── config/                     # 認證配置
├── user/                           # 👤 用戶模組
│   ├── controller/                 # 用戶控制器
│   ├── service/                    # 用戶服務
│   ├── dto/                        # 用戶相關DTO
│   ├── entity/                     # 用戶實體
│   └── repository/                 # 用戶倉庫
├── restaurant/                     # 🍴 餐廳模組
│   ├── controller/                 # 餐廳控制器
│   ├── service/                    # 餐廳服務
│   ├── dto/                        # 餐廳相關DTO
│   ├── entity/                     # 餐廳實體
│   └── repository/                 # 餐廳倉庫
├── review/                         # ⭐ 評論模組
│   ├── controller/                 # 評論控制器
│   ├── service/                    # 評論服務
│   ├── dto/                        # 評論相關DTO
│   ├── entity/                     # 評論實體
│   └── repository/                 # 評論倉庫
├── common/                         # 🛠️ 共用組件
│   ├── config/                     # 共用配置
│   ├── exception/                  # 異常處理
│   ├── util/                       # 工具類
│   └── constant/                   # 常數定義
├── security/                       # 🛡️ 安全模組
│   ├── config/                     # 安全配置
│   ├── filter/                     # 安全過濾器
│   └── util/                       # 安全工具類
├── cache/                          # ⚡ 緩存模組
│   ├── config/                     # 緩存配置
│   └── service/                    # 緩存服務
├── async/                          # 🔄 異步處理模組
│   ├── config/                     # 異步配置
│   └── service/                    # 異步服務
├── monitoring/                     # 📊 監控模組
│   ├── config/                     # 監控配置
│   └── service/                    # 監控服務
└── integration/                    # 🔗 外部集成模組
    ├── google/                     # 🌍 Google API集成
    ├── oauth2/                     # 🔑 OAuth2集成
    └── email/                      # ✉️ 郵件服務集成

前端資源 🖼️
src/main/resources/
├── templates/                      # 📄 Thymeleaf模板
│   ├── layout/                     # 佈局模板
│   ├── index.html                  # 首頁
│   ├── login.html                  # 登入頁面
│   └── register.html               # 註冊頁面
├── static/                         # 📁 靜態資源
│   ├── css/                        # 樣式檔案
│   ├── js/                         # JavaScript檔案
│   └── images/                     # 圖片資源
├── application.properties          # ⚙️ 應用程式配置
└── logback-spring.xml             # 📜 日誌配置

模組說明 📚
🔐 認證模組 (auth)

功能: 用戶登入、註冊、JWT token管理
主要組件: 
AuthController: 處理登入/註冊請求
AuthService: 認證業務邏輯
LoginRequest/LoginResponse/RegisterRequest: 認證相關DTO



👤 用戶模組 (user)

功能: 用戶資料管理、個人資料維護、收藏餐廳
主要組件:
UserController: 用戶資料CRUD操作
UserService: 用戶業務邏輯
User: 用戶實體類
UserRepository: 用戶資料存取



🍴 餐廳模組 (restaurant)

功能: 餐廳資訊管理、搜尋、地圖整合
主要組件:
RestaurantController: 餐廳CRUD操作
RestaurantService: 餐廳業務邏輯
Restaurant: 餐廳實體類
RestaurantRepository: 餐廳資料存取



⭐ 評論模組 (review)

功能: 餐廳評論、評分系統
主要組件:
ReviewController: 評論CRUD操作
ReviewService: 評論業務邏輯
Review: 評論實體類
ReviewRepository: 評論資料存取



🛠️ 共用組件 (common)

功能: 提供各模組共用的工具和配置
主要組件:
ApiResponse: 統一API回應格式
BusinessException: 業務異常處理
WebConfig: Web相關配置
各種工具類和常數



🛡️ 安全模組 (security)

功能: 應用程式安全控制
主要組件:
SecurityConfig: Spring Security配置
JwtUtil: JWT token工具類
安全過濾器和認證機制



⚡ 緩存模組 (cache)

功能: 提升應用程式效能
主要組件:
CacheConfig: 緩存配置
CacheService: 緩存服務



🔄 異步處理模組 (async)

功能: 處理耗時操作
主要組件:
AsyncConfig: 異步配置
AsyncService: 異步服務



📊 監控模組 (monitoring)

功能: 應用程式監控和日誌
主要組件:
MonitoringConfig: 監控配置
MonitoringService: 監控服務



🔗 外部集成模組 (integration)

功能: 與外部服務整合
主要組件:
GoogleIntegration: Google Maps API整合
OAuth2Integration: OAuth2認證整合
EmailService: 郵件發送服務



快速開始 🚀
環境需求

Java 17+
Maven 3.6+

啟動步驟

克隆專案

git clone [repository-url]
cd FoodMAP2


編譯專案

mvn clean compile


啟動應用程式

mvn spring-boot:run


訪問應用程式


首頁: http://localhost:8080
H2資料庫控制台: http://localhost:8080/h2-console

API文檔 📜
認證API

POST /api/auth/login - 用戶登入
POST /api/auth/register - 用戶註冊
GET /api/auth/check-email - 檢查郵箱是否存在

餐廳API

GET /api/restaurants - 取得所有餐廳
GET /api/restaurants/{id} - 取得特定餐廳
GET /api/restaurants/search - 搜尋餐廳

用戶API

GET /api/users/{id} - 取得用戶資料
PUT /api/users/{id} - 更新用戶資料

開發指南 🛠️
添加新功能

在對應模組下創建controller、service、entity等類別
遵循現有的命名規範和架構模式
添加適當的單元測試
更新API文檔

代碼規範

使用Lombok減少樣板代碼
遵循RESTful API設計原則
使用統一的異常處理機制
添加適當的日誌記錄

部署 ☁️
Docker部署
# 建構Docker映像
docker build -t foodmap2 .

# 運行容器
docker run -p 8080:8080 foodmap2

Kubernetes部署
kubectl apply -f deploy/kubernetes/

貢獻指南 🤝

Fork專案
創建功能分支 (git checkout -b feature/AmazingFeature)
提交變更 (git commit -m 'Add some AmazingFeature')
推送到分支 (git push origin feature/AmazingFeature)
開啟Pull Request

授權 📜
本專案採用 MIT 授權條款 - 詳見 LICENSE 檔案
聯絡資訊 📧

專案維護者: [Your Name]
電子郵件: [your.email@example.com]
專案連結: https://github.com/yourusername/foodmap2
