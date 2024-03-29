---
title: Pagination 分页组件
description:
type: 0
group: ⚙ 组件
menuName: Pagination
icon:
order: 73
---

分页组件

```schema: scope="body"
{
    "type": "service",
    "api": "/api/mock2/crud/table",
    "body": [
        {
            "type": "pagination",
            "layout": "total,perPage,pager,go",
            "mode": "normal",
            "activePage": 2,
            "lastPage": 99999,
            "total": 999,
            "perPage": 10,
            "maxButtons": 7,
            "showPerPage": true,
            "perPageAvailable": [10, 20, 50, 100],
            "showPageInput": true,
            "disabled": false

        }
    ]
}
```

### 简易模式

```schema: scope="body"
{
    "type": "service",
    "api": "/api/mock2/crud/table",
    "body": [
        {
            "type": "pagination",
            "mode": "simple",
            "activePage": 2,
            "hasNext": true
        }
    ]
}
```

## 属性表

| 属性名           | 类型                       | 默认值                                   | 说明                                                      |
| ---------------- | -------------------------- | ---------------------------------------- | --------------------------------------------------------- |
| type             | `string`                   | `"pagination"`                           | 指定为 Pagination 渲染器                                  |
| mode             | `normal` \| `simple`       | `normal`                                 | 迷你版本/简易版本 只显示左右箭头，配合 hasNext 使用       |
| layout           | `string` \| `string[]`     | `["pager"]`                              | 通过控制 layout 属性的顺序，调整分页结构布局              |
| maxButtons       | `number` \| `string`       | `5`                                      | 最多显示多少个分页按钮，最小为 5                          |
| total            | `number` \| `string`       |                                          | 总条数                                                    |
| activePage       | `number` \| `string`       | `1`                                      | 当前页数                                                  |
| perPage          | `number` \| `string`       | `10`                                     | 每页显示多条数据                                          |
| showPerPage      | `boolean`                  | false                                    | 是否展示 perPage 切换器 layout 和 showPerPage 都可以控制  |
| perPageAvailable | `number[]`                 | `[10, 20, 50, 100]`                      | 指定每页可以显示多少条                                    |
| showPageInput    | `boolean`                  | false                                    | 是否显示快速跳转输入框 layout 和 showPageInput 都可以控制 |
| disabled         | `boolean`                  | false                                    | 是否禁用                                                  |
| onPageChange     | page、perPage 改变时会触发 | (page: number, perPage: number) => void; | 分页改变触发                                              |
