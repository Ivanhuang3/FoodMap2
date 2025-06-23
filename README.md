# FoodMAP2 專案架構 🍽️

## 專案概述 📖
FoodMAP2 是一個基於 Spring Boot 的美食地圖應用程式，提供餐廳搜尋、評論和用戶管理功能，旨在為用戶打造個人化的美食探索體驗。

## 技術棧 ⚙️
- **後端框架**: Spring Boot 3.2.3
- **資料庫**: H2 (開發環境)
- **安全框架**: Spring Security + JWT
- **模板引擎**: Thymeleaf
- **緩存**: Caffeine
- **建構工具**: Maven
- **Java版本**: 17

## 專案結構 📂

```plaintext
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

