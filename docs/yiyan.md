# 每日一言随机获取接口使用教程

## 接口概述

由xby制作，lcy提供服务。 该接口提供随机每日一言的获取功能，可以通过指定参数来筛选特定的每日一言。

## 接口地址

```
https://api.lcy-ys.top/api/yiyan
```

## 请求方法

`GET`

## 功能描述

  * **随机获取每日一言** ：不带任何参数时，将随机返回一个每日一言。
  * **按 serial_number 筛选** ：通过指定 `serial_number` 参数，可以获取特定编号的每日一言。

## 参数说明

参数名 | 类型 | 是否必填 | 描述
---|---|---|---
serial_number | Number | 可选 | 每日一言的编号，用于筛选特定方程式

## 响应格式

返回的数据为 JSON 格式，包含以下字段：

字段名 | 类型 | 描述
---|---|---
content | String | 每日一言的内容
author | String | 一言的提供者
serial_number | Number | 一言的编号
interpretation | String | 一言的解释

## 调用示例

### 随机获取每日一言

请求：

```http
GET https://api.lcy-ys.top/api/yiyan
```

响应示例：

```json
{
  "content": "每天给自己一个微笑，开启美好一天。",
  "author": "xby",
  "serial_number": 52,
  "interpretation": "以微笑开始一天，能带来好心情和积极状态"
}
```

## 错误处理

如果请求的 `serial_number` 不存在，将返回 404 错误：

```json
{
  "error": "Not found"
}
```

## 注意事项

  * 确保请求的域名与实际部署的域名一致。
  * 如果需要频繁调用，请注意控制请求频率，避免对服务器造成过大压力。
