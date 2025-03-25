%% 修正版前端流程图
graph LR
  A[编辑Details页面] --> B[点击“Consolidate”按钮]
  B --> C{调用保存状态接口}
  C -->|未保存| D[显示保存提示弹窗]
  D --> E[点击“OK”按钮]
  E --> A
  C -->|已保存| F[调用生成Consolidate接口]
  F --> G[跳转Consol新增页面]
  G --> H[渲染预填表单]
  H --> I[点击“保存”按钮]
  I --> J[调用创建Consol接口]
  J -->|失败| K[标红错误字段]
  J -->|成功| L[显示Success提示]
  L --> M[刷新Consol OverView]
  M --> N[隐藏原Booking记录]

  style A fill:#E1F5FE,stroke:#039BE5
  style C fill:#C8E6C9,stroke:#43A047
  style F fill:#C8E6C9,stroke:#43A047
  style J fill:#C8E6C9,stroke:#43A047
