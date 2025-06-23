- **專案概述**：FoodMAP2 是一個基於 Spring Boot 的美食地圖應用程式，提供餐廳搜尋、評論和用戶管理功能。
- **技術棧**：使用 Spring Boot 3.2.3、H2 資料庫（開發環境）、Spring Security + JWT、安全框架、Thymeleaf 模板引擎、Caffeine 緩存、Maven 建構工具和 Java 17。
- **專案結構**：包含多個模組，如認證（auth）、用戶管理（user）、餐廳管理（restaurant）等，結構清晰，易於維護。

#### 專案結構
以下是 FoodMAP2 的目錄結構
```
src/main/java/com/foodmap2/
├── auth/
│   ├── controller/
│   ├── service/
│   ├── dto/
│   └── config/
├── user/
│   ├── controller/
│   ├── service/
│   ├── dto/
│   ├── entity/
│   └── repository/
├── restaurant/
│   ├── controller/
│   ├── service/
│   ├── dto/
│   ├── entity/
│   └── repository/
├── review/
│   ├── controller/
│   ├── service/
│   ├── dto/
│   ├── entity/
│   └── repository/
├── common/
│   ├── config/
│   ├── exception/
│   ├── util/
│   └── constant/
├── security/
│   ├── config/
│   ├── filter/
│   └── util/
├── cache/
│   ├── config/
│   └── service/
├── async/
│   ├── config/
│   └── service/
├── monitoring/
│   ├── config/
│   └── service/
└── integration/
    ├── google/
    ├── oauth2/
    └── email/
```

#### 前端資源
```
src/main/resources/
├── templates/
│   ├── layout/
│   ├── index.html
│   ├── login.html
│   └── register.html
├── static/
│   ├── css/
│   ├── js/
│   └── images/
├── application.properties
└── logback-spring.xml
```

#### 快速開始
- **環境需求**：Java 17+ 和 Maven 3.6+。
- **啟動步驟**：
  1. 克隆專案：`git clone [repository-url]; cd FoodMAP2`
  2. 編譯：`mvn clean compile`
  3. 運行：`mvn spring-boot:run`
  4. 訪問：首頁 [invalid url, do not cite]，H2 控制台 [invalid url, do not cite]/h2-console。

---

### 以下是 FoodMAP2 專案的詳細架構說明，供您參考：

FoodMAP2 是一個基於 Spring Boot 的美食地圖應用程式，旨在提供餐廳搜尋、評論管理以及用戶個人化功能的後端服務。以下是專案的技術棧、架構設計和使用指南，適合開發者快速上手和貢獻。

#### 技術棧
專案採用以下技術棧：
- **後端框架**：Spring Boot 3.2.3，提供快速開發和整合能力。
- **資料庫**：H2 資料庫用於開發環境，方便本地測試。
- **安全框架**：Spring Security 結合 JWT 實現用戶認證和授權。
- **模板引擎**：Thymeleaf，用於前端頁面渲染。
- **緩存**：Caffeine，提供高效的本地緩存機制。
- **建構工具**：Maven，管理依賴和建構流程。
- **Java 版本**：17，確保現代 Java 特性的支持。

#### 專案結構
專案採用模組化設計，目錄結構如下，位於 `src/main/java/com/foodmap2/` 下：

```
src/main/java/com/foodmap2/
├── auth/                           # 認證模組
│   ├── controller/                 # 認證控制器，如處理登入/註冊請求
│   ├── service/                    # 認證服務，如用戶註冊邏輯
│   ├── dto/                        # 認證相關 DTO，如 LoginRequest
│   └── config/                     # 認證配置，如 Spring Security 設置
├── user/                           # 用戶模組
│   ├── controller/                 # 用戶控制器，如用戶資料 CRUD
│   ├── service/                    # 用戶服務，如更新個人資料
│   ├── dto/                        # 用戶相關 DTO，如 UserDTO
│   ├── entity/                     # 用戶實體，如 User
│   └── repository/                 # 用戶倉庫，如 UserRepository
├── restaurant/                     # 餐廳模組
│   ├── controller/                 # 餐廳控制器，如餐廳搜尋 API
│   ├── service/                    # 餐廳服務，如推薦邏輯
│   ├── dto/                        # 餐廳相關 DTO，如 RestaurantDTO
│   ├── entity/                     # 餐廳實體，如 Restaurant
│   └── repository/                 # 餐廳倉庫，如 RestaurantRepository
├── review/                         # 評論模組
│   ├── controller/                 # 評論控制器，如評論 CRUD
│   ├── service/                    # 評論服務，如評分計算
│   ├── dto/                        # 評論相關 DTO，如 ReviewDTO
│   ├── entity/                     # 評論實體，如 Review
│   └── repository/                 # 評論倉庫，如 ReviewRepository
├── common/                         # 共用組件
│   ├── config/                     # 共用配置，如 Web 配置
│   ├── exception/                  # 異常處理，如 BusinessException
│   ├── util/                       # 工具類，如日期格式化
│   └── constant/                   # 常數定義，如角色名稱
├── security/                       # 安全模組
│   ├── config/                     # 安全配置，如 JWT 過濾器
│   ├── filter/                     # 安全過濾器，如 JwtAuthorizationFilter
│   └── util/                       # 安全工具類，如 JwtUtil
├── cache/                          # 緩存模組
│   ├── config/                     # 緩存配置，如 Caffeine 配置
│   └── service/                    # 緩存服務，如快取用戶資料
├── async/                          # 異步處理模組
│   ├── config/                     # 異步配置，如任務執行器
│   └── service/                    # 異步服務，如郵件發送
├── monitoring/                     # 監控模組
│   ├── config/                     # 監控配置，如 Actuator 端點
│   └── service/                    # 監控服務，如日誌記錄
└── integration/                    # 外部集成模組
    ├── google/                     # Google API 集成，如地圖服務
    ├── oauth2/                     # OAuth2 集成，如 Google 登入
    └── email/                      # 郵件服務集成，如發送通知
```

此外，前端資源位於 `src/main/resources/` 下：

```
src/main/resources/
├── templates/                      # Thymeleaf 模板
│   ├── layout/                     # 佈局模板，如共用頁面框架
│   ├── index.html                  # 首頁模板
│   ├── login.html                  # 登入頁面模板
│   └── register.html               # 註冊頁面模板
├── static/                         # 靜態資源
│   ├── css/                        # CSS 檔案，如樣式表
│   ├── js/                         # JavaScript 檔案，如前端邏輯
│   └── images/                     # 圖片資源，如 logo
├── application.properties          # 應用程式配置，如資料庫連接
└── logback-spring.xml             # 日誌配置，如記錄級別
```

#### 模組說明
以下是各模組的功能和主要組件概述：

| 模組名稱       | 功能描述                                      | 主要組件示例                     |
|----------------|-----------------------------------------------|-----------------------------------|
| auth           | 處理用戶登入、註冊和 JWT token 管理           | `AuthController`, `AuthService`   |
| user           | 管理用戶資料，如個人資料更新和收藏餐廳         | `UserController`, `UserRepository`|
| restaurant     | 管理餐廳資訊，如搜尋和地圖整合                | `RestaurantService`, `Restaurant` |
| review         | 處理餐廳評論和評分系統                        | `ReviewController`, `ReviewDTO`   |
| common         | 提供共用工具和配置，如異常處理和常數           | `ApiResponse`, `BusinessException`|
| security       | 實現應用程式安全控制，如 JWT 和角色驗證        | `SecurityConfig`, `JwtUtil`       |
| cache          | 提升效能，使用緩存如 Caffeine                  | `CacheConfig`, `CacheService`     |
| async          | 處理異步任務，如郵件通知和定時任務            | `AsyncConfig`, `AsyncService`     |
| monitoring     | 提供應用程式監控和日誌記錄                    | `MonitoringConfig`, `MonitoringService`|
| integration    | 整合外部服務，如 Google Maps 和郵件服務        | `GoogleIntegration`, `EmailService`|

#### 快速開始
要快速啟動 FoodMAP2，需滿足以下環境需求：
- Java 17 或更高版本
- Maven 3.6 或更高版本

啟動步驟如下：
1. 克隆專案：
   ```bash
   git clone [repository-url]
   cd FoodMAP2
   ```
2. 編譯專案：
   ```bash
   mvn clean compile
   ```
3. 運行應用程式：
   ```bash
   mvn spring-boot:run
   ```
4. 訪問應用程式：
   - 首頁： [invalid url, do not cite]
   - H2 資料庫控制台： [invalid url, do not cite]/h2-console

#### API 文檔
以下是一些關鍵 API 端點：

| API 端點               | 方法 | 描述               |
|-----------------------|------|--------------------|
| `/api/auth/login`     | POST | 用戶登入           |
| `/api/auth/register`  | POST | 用戶註冊           |
| `/api/auth/check-email`| GET | 檢查郵箱是否存在   |
| `/api/restaurants`    | GET  | 取得所有餐廳       |
| `/api/restaurants/{id}`| GET | 取得特定餐廳       |
| `/api/restaurants/search`| GET | 搜尋餐廳           |
| `/api/users/{id}`     | GET  | 取得用戶資料       |
| `/api/users/{id}`     | PUT  | 更新用戶資料       |

#### 開發指南
開發新功能時，請遵循以下規範：
- 在對應模組下創建控制器、服務、實體等類別。
- 使用 Lombok 減少樣板代碼。
- 遵循 RESTful API 設計原則。
- 實現統一的異常處理機制。
- 添加適當的日誌記錄。
- 為新功能撰寫單元測試，並更新 API 文檔。

#### 部署
部署方式包括 Docker 和 Kubernetes：
- **Docker 部署**：
  ```bash
  docker build -t foodmap2 .
  docker run -p 8080:8080 foodmap2
  ```
- **Kubernetes 部署**：
  ```bash
  kubectl apply -f deploy/kubernetes/
  ```

#### 貢獻指南
貢獻流程如下：
1. Fork 專案。
2. 創建功能分支：`git checkout -b feature/AmazingFeature`
3. 提交變更：`git commit -m 'Add some AmazingFeature'`
4. 推送到分支：`git push origin feature/AmazingFeature`
5. 開啟 Pull Request。

#### 授權
本專案採用 MIT 授權條款 - 詳見 [LICENSE](LICENSE) 檔案。

#### 聯絡資訊
- 專案維護者：[您的姓名]
- 電子郵件：[your.email@example.com]
- 專案連結：[[invalid url, do not cite])
