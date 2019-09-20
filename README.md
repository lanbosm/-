# account账号信息
>维护人员：**lanbo**  
>创建时间：2016-04-06


##通用

### POST http://192.168.14.83:3000/user/login  
>登录

#### 请求头 


#### 请求参数

```javascript
{
    "userName": "13636574272@163.com",
    "password": "123456"
}
````

#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "token": "uzvqjvtvggi8pd9g1o3n0domc"
    },
    "message": "登录成功"
}
```

##图表


### POST - 接口未知
>获取表名 前端目前写死


#### 请求头 


#### 请求参数


#### 返回成功JSON示例
```javascript
export const tables = [
  { id: 2496, name: 'order_analysis' },
  { id: 2000, name: 'rz_fin_report'} //定义表名和id
]
```


#### GET http://192.168.14.83:3000/exesql?sql=desc%20rz_fin_report
>查询表


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'desc rz_fin_report'
}
````

#### 返回成功JSON示例
```javascript
 {
    "code": 20000,
    "data": [{
        "Field": "ID",
        "Type": "varchar(32)",
        "Null": "NO",
        "Key": "PRI",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "ENTERPRISE_ID",
        "Type": "varchar(32)",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "ENTERPRISE_NAME",
        "Type": "varchar(240)",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "PERIOD_TYPE",
        "Type": "varchar(50)",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "PERIOD_DATE",
        "Type": "date",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FINUNIT",
        "Type": "varchar(50)",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FAX_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FAX_LAST_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FAX_INCREASED",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FIXEDASSETS_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FIXEDASSETS_LAST_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "FIXEDASSETS_INCREASED",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "REVENUE_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "REVENUE_LAST_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "REVENUE_INCREASED",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "PROFIT_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "PROFIT_LAST_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "PROFIT_INCREASED",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "OTHER_VALUE",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "OTHER_INCREASED",
        "Type": "double",
        "Null": "YES",
        "Key": "",
        "Default": null,
        "Extra": ""
    }, {
        "Field": "STATUS",
        "Type": "int(3)",
        "Null": "YES",
        "Key": "",
        "Default": "0",
        "Extra": ""
    }]
}
```



#### GET http://192.168.14.83:3000/exesql?sql=SELECT%20ENTERPRISE_NAME%20FROM%20rz_fin_report%20%20GROUP%20BY%20ENTERPRISE_NAME%20%20LIMIT%20200
>创建图表唯度


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'SELECT ENTERPRISE_NAME FROM rz_fin_report  GROUP BY ENTERPRISE_NAME  LIMIT 200'
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": [{
        "enterprise_name": "嘉兴市琪宸智能化工程有限公司"
    }, {
        "enterprise_name": "嘉兴爱嘉装饰工程有限公司"
    }]
}
```





### GET http://192.168.14.83:3000/exesql?sql=SELECT%20ENTERPRISE_NAME%20FROM%20rz_fin_report%20%20GROUP%20BY%20ENTERPRISE_NAME%20%20LIMIT%20200 
>创建图表数值


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'SELECT sum(FAX_VALUE) as FAX_VALUE,ENTERPRISE_NAME FROM rz_fin_report  GROUP BY ENTERPRISE_NAME  LIMIT 200'
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": [{
        "fax_value": 226,
        "enterprise_name": "嘉兴市琪宸智能化工程有限公司"
    }, {
        "fax_value": 230,
        "enterprise_name": "嘉兴爱嘉装饰工程有限公司"
    }]
}
```



### GET http://192.168.14.83:3000/exesql?sql=SELECT%20avg(FAX_VALUE)%20as%20FAX_VALUE,ENTERPRISE_NAME%20FROM%20rz_fin_report%20%20GROUP%20BY%20ENTERPRISE_NAME%20ORDER%20BY%20FAX_VALUE%20desc%20LIMIT%20200
>创建图表的排序规则


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'SELECT avg(FAX_VALUE) as FAX_VALUE,ENTERPRISE_NAME FROM rz_fin_report  GROUP BY ENTERPRISE_NAME ORDER BY FAX_VALUE desc LIMIT 200'
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": [{
        "fax_value": 115,
        "enterprise_name": "嘉兴爱嘉装饰工程有限公司"
    }, {
        "fax_value": 113,
        "enterprise_name": "嘉兴市琪宸智能化工程有限公司"
    }]

```


### GET http://192.168.14.83:3000/exesql?sql=SELECT%20avg(FAX_VALUE)%20as%20FAX_VALUE,ENTERPRISE_NAME%20FROM%20rz_fin_report%20%20GROUP%20BY%20ENTERPRISE_NAME%20ORDER%20BY%20FAX_VALUE%20desc%20LIMIT%20200
>创建图表的排序规则


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'SELECT avg(FAX_VALUE) as FAX_VALUE,ENTERPRISE_NAME FROM rz_fin_report  GROUP BY ENTERPRISE_NAME ORDER BY FAX_VALUE desc LIMIT 200'
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": [{
        "fax_value": 115,
        "enterprise_name": "嘉兴爱嘉装饰工程有限公司"
    }, {
        "fax_value": 113,
        "enterprise_name": "嘉兴市琪宸智能化工程有限公司"
    }]

```
#### 返回错误JSON示例
```javascript


### GET http://192.168.14.83:3000/exesql?sql=SELECT%20avg(FAX_VALUE)%20as%20FAX_VALUE,ENTERPRISE_NAME%20FROM%20rz_fin_report%20%20GROUP%20BY%20ENTERPRISE_NAME%20ORDER%20BY%20FAX_VALUE%20desc%20LIMIT%20200
>创建图表的筛选条件


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    sql:'SELECT avg(FAX_VALUE) as FAX_VALUE,ENTERPRISE_NAME FROM rz_fin_report  GROUP BY ENTERPRISE_NAME ORDER BY FAX_VALUE desc LIMIT 200'
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": [{
        "fax_value": 115,
        "enterprise_name": "嘉兴爱嘉装饰工程有限公司"
    }, {
        "fax_value": 113,
        "enterprise_name": "嘉兴市琪宸智能化工程有限公司"
    }]

```




### POST - 接口未知
>创建图表筛选规则 功能报错


#### 请求头 


#### 请求参数


#### 返回成功JSON示例
```

```
#### 返回错误JSON示例
```javascript


```


### POST http://192.168.14.83:3000/chart
>保存图表


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    "chart_name": "测试图表",
    "desc": "测试图表描述",
    "content": {
        "dataSrc": "rz_fin_report",
        "orderByStrs": ["FAX_VALUE desc"],
        "limit": 200,
        "selectedCalcul": [{
            "Column": "FAX_VALUE",
            "calculFunc": "sum",
            "Type": "double",
            "availableFunc": [{
                "name": "合计",
                "func": "sum"
            }, {
                "name": "平均",
                "func": "avg"
            }, {
                "name": "最大值",
                "func": "max"
            }, {
                "name": "最小值",
                "func": "min"
            }, {
                "name": "计数",
                "func": "count"
            }, {
                "name": "无",
                "func": "none"
            }],
            "name": "FAX_VALUE",
            "lable": "FAX_VALUE(合计)"
        }],
        "selectedDimension": [{
            "Column": "ENTERPRISE_NAME",
            "Type": "varchar(240)",
            "id": 2,
            "isDimension": true,
            "name": "ENTERPRISE_NAME",
            "lable": "ENTERPRISE_NAME",
            "asxAxis": true
        }],
        "chartType": "line",
        "filters": []
    }
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "id": "5d8492edf884af0068693a2d"
    }
}
```



### GET http://192.168.14.83:3000/chart?id=5d8492edf884af0068693a2d
>根据图表id获取图表


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    "id":"5d8492edf884af0068693a2d"
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "creator": "5d84750eba39c80073058fac",
        "desc": "测试图表描述",
        "content": {
            "dataSrc": "rz_fin_report",
            "orderByStrs": ["FAX_VALUE desc"],
            "limit": 200,
            "selectedCalcul": [{
                "Column": "FAX_VALUE",
                "calculFunc": "sum",
                "Type": "double",
                "availableFunc": [{
                    "name": "合计",
                    "func": "sum"
                }, {
                    "name": "平均",
                    "func": "avg"
                }, {
                    "name": "最大值",
                    "func": "max"
                }, {
                    "name": "最小值",
                    "func": "min"
                }, {
                    "name": "计数",
                    "func": "count"
                }, {
                    "name": "无",
                    "func": "none"
                }],
                "name": "FAX_VALUE",
                "lable": "FAX_VALUE(合计)"
            }],
            "selectedDimension": [{
                "Column": "ENTERPRISE_NAME",
                "Type": "varchar(240)",
                "id": 2,
                "isDimension": true,
                "name": "ENTERPRISE_NAME",
                "lable": "ENTERPRISE_NAME",
                "asxAxis": true
            }],
            "chartType": "line",
            "filters": []
        },
        "chart_name": "测试图表",
        "status": 1,
        "isPrivate": false,
        "objectId": "5d8492edf884af0068693a2d",
        "createdAt": "2019-09-20T08:50:53.969Z",
        "updatedAt": "2019-09-20T08:50:53.969Z"
    }
}
```



##仪表盘


### GET http://192.168.14.83:3000/dashboard/list
>仪表盘列表


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "dashboards": [{
            "creator": "5d84750eba39c80073058fac",
            "desc": "测试看板描述",
            "content": {
                "layout": [{
                    "id": "5d8492edf884af0068693a2d",
                    "x": 0,
                    "y": 0,
                    "w": 12,
                    "h": 9,
                    "i": "5d8492edf884af0068693a2d"
                }]
            },
            "name": "测试看板",
            "status": 1,
            "isPrivate": false,
            "objectId": "5d849d04ba39c800730702c3",
            "createdAt": "2019-09-20T09:33:56.661Z",
            "updatedAt": "2019-09-20T10:37:45.876Z"
        }, {
            "creator": "5d84750eba39c80073058fac",
            "desc": "刘地利的图表描述",
            "content": {
                "layout": [{
                    "id": "5d8492edf884af0068693a2d",
                    "x": 0,
                    "y": 0,
                    "w": 12,
                    "h": 9,
                    "i": "5d8492edf884af0068693a2d"
                }]
            },
            "name": "刘地利的图表",
            "status": 1,
            "isPrivate": false,
            "objectId": "5d84a8476e9ba10068beb28d",
            "createdAt": "2019-09-20T10:21:59.847Z",
            "updatedAt": "2019-09-20T10:37:12.226Z"
        }],
        "order": ["5d84a8476e9ba10068beb28d", "5d849d04ba39c800730702c3"]
    }
}
```





### POST http://192.168.14.83:3000/dashboard
>添加仪表盘


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    "name": "刘地利的图表",
    "desc": "刘地利的图表描述"
}
````
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "id": "5d84a8476e9ba10068beb28d"
    }
}
```



### POST http://192.168.14.83:3000/dashboard/list
>添加图加到仪表盘 (第一步)


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    "chart_id":"5d8492edf884af0068693a2d",
    "dashboard_id":"5d84a8476e9ba10068beb28d"
}
```
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "success": true
    }
}
```



### POST http://192.168.14.83:3000/dashboard/list
>添加图加到仪表盘 (第二步)


#### 请求头 

DS-Token: uzvqjvtvggi8pd9g1o3n0domc
Content-Type: application/json; charset=utf-8

#### 请求参数
```javascript
{
    "creator": "5d84750eba39c80073058fac",
    "desc": "测试看板描述",
    "content": {
        "layout": [{
            "id": "5d8492edf884af0068693a2d",
            "x": 0,
            "y": 0,
            "w": 12,
            "h": 9,
            "i": "5d8492edf884af0068693a2d"
        }]
    },
    "name": "测试看板",
    "status": 1,
    "isPrivate": false,
    "objectId": "5d849d04ba39c800730702c3",
    "createdAt": "2019-09-20T09:33:56.661Z",
    "updatedAt": "2019-09-20T10:20:48.983Z"
}

```
#### 返回成功JSON示例
```javascript
{
    "code": 20000,
    "data": {
        "id": "5d849d04ba39c800730702c3"
    }
}
```





### POST http://192.168.14.83:3000/dashboard/list
>添加图加到仪表盘 (第二步)


#### localhost:8080/vue-data-board#/fullscreendb/5d849d04ba39c800730702c3
>分享链接

无接口

#### 请求参数
```javascript
{
    
}

```
#### 返回成功JSON示例
```javascript
{
   
}
```
