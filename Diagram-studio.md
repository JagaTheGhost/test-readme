# Diagram-studio

The purpose of the document is to test the mermaid diagram studio works corectly.

By going across all the sub tabs,
- **flowchart**
- **Sequence** 
- **er model** 
- **class**
- **state**
- **git graph**
- **mind tree**

```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
flowchart TD
  subgraph Public_Zone ["Public DMZ & Ingress"]
    CDN([Cloudflare Edge CDN])
    APIGW[API Gateway :: Envoy]
    CDN -->|HTTPS / WSS| APIGW
  end

  subgraph Private_Mesh ["Private Service Mesh (K8s)"]
    APIGW --> AuthSvc[Auth & Policy Svc]
    APIGW --> AppSvc[Core Application API]
    APIGW --> PaymentSvc[Payment Processing Svc]
    AppSvc --> Worker[Background Task Worker]
  end

  subgraph Data_Tier ["Persistence & Streaming Tier"]
    AppSvc --> Cache[(Redis Cache Cluster)]
    AppSvc --> DB[(PostgreSQL Primary)]
    Worker -->|Async Events| Broker{{Kafka Event Bus}}
    PaymentSvc --> Stripe([Stripe External API])
  end

  style Public_Zone fill:#1e1e38,stroke:#6366f1,stroke-width:1px
  style Private_Mesh fill:#152238,stroke:#38bdf8,stroke-width:1px
  style Data_Tier fill:#1a2822,stroke:#10b981,stroke-width:1px
```

```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
sequenceDiagram
  autonumber
  actor User as End User
  participant SPA as Single Page App (Client)
  participant IdP as Identity Provider (OAuth2 / OIDC)
  participant API as Backend Resource Server

  User->>SPA: Click "Sign in with GitHub/Google"
  SPA->>SPA: Generate code_verifier & code_challenge (PKCE)
  SPA->>IdP: GET /oauth/authorize (challenge, client_id, scopes)
  IdP->>User: Display Consent Dialog
  User->>IdP: Grant Consent
  IdP-->>SPA: Redirect with Authorization Code
  SPA->>IdP: POST /oauth/token (code, code_verifier)
  IdP-->>SPA: 200 OK (access_token, id_token, refresh_token)
  SPA->>API: GET /api/v1/user/profile (Bearer access_token)
  API->>API: Verify JWT signature & scopes
  API-->>SPA: 200 OK (User Profile JSON)
  SPA-->>User: Render Dashboard UI
```
```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
erDiagram
  USERS ||--o{ ORDERS : places
  USERS ||--|| PROFILES : has
  ORDERS ||--|{ ORDER_ITEMS : contains
  PRODUCTS ||--o{ ORDER_ITEMS : referenced_in
  CATEGORIES ||--o{ PRODUCTS : categorizes
  ORDERS ||--|| PAYMENTS : settled_by

  USERS {
    uuid id PK
    string email UK
    string password_hash
    string full_name
    timestamp created_at
  }

  PROFILES {
    uuid id PK
    uuid user_id FK
    string avatar_url
    string phone_number
    string shipping_address
  }

  ORDERS {
    uuid id PK
    uuid user_id FK
    string order_number UK
    decimal total_amount
    string status
    timestamp placed_at
  }

  ORDER_ITEMS {
    uuid id PK
    uuid order_id FK
    uuid product_id FK
    int quantity
    decimal unit_price
  }

  PRODUCTS {
    uuid id PK
    uuid category_id FK
    string sku UK
    string title
    decimal price
    int stock_quantity
  }

  CATEGORIES {
    uuid id PK
    string slug UK
    string name
    string description
  }

  PAYMENTS {
    uuid id PK
    uuid order_id FK
    string provider
    string transaction_ref
    decimal amount
    string status
  }
```

```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
classDiagram
  class UserEntity {
    +UUID id
    +String email
    +String fullName
    +validateEmail() Boolean
    +changePassword(String hash) void
  }

  class UserRepositoryPort {
    <<interface>>
    +findById(UUID id) UserEntity
    +save(UserEntity user) UserEntity
    +delete(UUID id) Boolean
  }

  class RegisterUserUseCase {
    -UserRepositoryPort userRepo
    -HasherPort hasher
    +execute(RegisterDTO dto) UserEntity
  }

  class PostgresUserAdapter {
    -DatabaseClient client
    +findById(UUID id) UserEntity
    +save(UserEntity user) UserEntity
    +delete(UUID id) Boolean
  }

  class UserRestController {
    -RegisterUserUseCase registerUseCase
    +handlePost(Request req) Response
  }

  RegisterUserUseCase --> UserRepositoryPort : depends on
  RegisterUserUseCase --> UserEntity : returns
  PostgresUserAdapter ..|> UserRepositoryPort : implements
  UserRestController --> RegisterUserUseCase : invokes
```
```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
stateDiagram-v2
  [*] --> Created : Cart Submitted
  
  Created --> PaymentPending : Payment Intent Issued
  PaymentPending --> PaymentFailed : Card Declined / Timeout
  PaymentFailed --> PaymentPending : Customer Retries
  PaymentFailed --> Cancelled : Auto-expire 24h

  PaymentPending --> Paid : Webhook Confirmed
  Paid --> Processing : Pick & Pack Started
  Processing --> Shipped : Carrier Label Scanned
  
  Shipped --> OutForDelivery : Local Hub Arrival
  OutForDelivery --> Delivered : Customer Signed
  Delivered --> [*]

  Paid --> RefundRequested : Dispute Opened
  RefundRequested --> Refunded : Approved
  Refunded --> [*]
  Cancelled --> [*]
```

```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
gitGraph
  commit id: "v1.0.0"
  branch develop
  checkout develop
  commit id: "feat: setup core"
  branch feature/user-auth
  checkout feature/user-auth
  commit id: "feat: login route"
  commit id: "feat: jwt session"
  checkout develop
  merge feature/user-auth id: "PR #12 merged"
  branch release/v1.1.0
  checkout release/v1.1.0
  commit id: "chore: bump version"
  checkout main
  merge release/v1.1.0 tag: "v1.1.0"
  checkout develop
  merge release/v1.1.0
  checkout main
  branch hotfix/auth-leak
  checkout hotfix/auth-leak
  commit id: "fix: sanitize tokens"
  checkout main
  merge hotfix/auth-leak tag: "v1.1.1"
  checkout develop
  merge hotfix/auth-leak
```

```mermaid
%%{init: {"theme":"base","themeVariables":{"darkMode":true,"background":"#002b36","primaryColor":"#073642","primaryTextColor":"#93a1a1","textColor":"#93a1a1","nodeTextColor":"#93a1a1","mainBkg":"#073642","primaryBorderColor":"#268bd2","lineColor":"#2aa198","secondaryColor":"#001e26","tertiaryColor":"#073642","actorBorder":"#268bd2","actorBkg":"#073642","actorTextColor":"#93a1a1","actorLineColor":"#2aa198","signalColor":"#2aa198","signalTextColor":"#93a1a1","fontFamily":"Inter, sans-serif","fontSize":"13px","mindmapRootColor":"#268bd2","mindmapRootTextColor":"#ffffff","cScale0":"#268bd2","cScaleLabel0":"#ffffff","cScale1":"#2aa198","cScaleLabel1":"#ffffff","cScale2":"#859900","cScaleLabel2":"#ffffff","cScale3":"#b58900","cScaleLabel3":"#ffffff","cScale4":"#cb4b16","cScaleLabel4":"#ffffff","cScale5":"#dc322f","cScaleLabel5":"#ffffff","cScale6":"#d33682","cScaleLabel6":"#ffffff","cScale7":"#6c71c4","cScaleLabel7":"#ffffff"}}}%%
mindmap
  root((Platform Engineering))
    Infrastructure as Code
      Terraform
      OpenTofu
      Pulumi
      AWS CDK
    Containers & Orchestration
      Docker
      Kubernetes
      Helm Charts
      ArgoCD GitOps
    CI / CD Pipelines
      GitHub Actions
      GitLab CI
      Tekton
    Observability & SRE
      Prometheus Metrics
      Grafana Dashboards
      OpenTelemetry Tracing
      Loki Log Aggregation
    Security & Policy
      Trivy Scanner
      Falco Runtime Guard
      HashiCorp Vault
      Cosign Image Sign
```