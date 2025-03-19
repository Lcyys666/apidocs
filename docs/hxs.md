# 化学方程式随机获取接口使用教程

## 接口概述
由xby制作，lcy提供服务。
该接口提供随机化学方程式的获取功能，可以通过指定参数来筛选特定的化学方程式。

## 接口地址

```
https://api.lcy-ys.top/api/random
```

## 请求方法

`GET`

## 功能描述

  * **随机获取化学方程式** ：不带任何参数时，将随机返回一个化学方程式。
  * **按 serial_number 筛选** ：通过指定 `serial_number` 参数，可以获取特定编号的化学方程式。

## 参数说明

参数名 | 类型 | 是否必填 | 描述
---|---|---|---
serial_number | Number | 可选 | 化学方程式的编号，用于筛选特定方程式

## 响应格式

返回的数据为 JSON 格式，包含以下字段：

字段名 | 类型 | 描述
---|---|---
content | String | 化学方程式的内容
author | String | 方程式的提交者
serial_number | Number | 方程式的编号
interpretation | String | 方程式的解释

## 调用示例

### 随机获取化学方程式

请求：

```http
GET https://api.lcy-ys.top/api/random
```

响应示例：

```json
{
  "content": "C + O2 → CO2",
  "author": "xby",
  "serial_number": 1,
  "interpretation": "碳与氧气在点燃条件下反应生成二氧化碳"
}
```

### 按 serial_number 筛选

请求：

```http
GET https://api.lcy-ys.top/api/random?serial_number=2
```

响应示例：

```json
{
  "content": "2H2 + O2 → 2H2O",
  "author": "xby",
  "serial_number": 2,
  "interpretation": "氢气与氧气在点燃条件下反应生成水"
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
