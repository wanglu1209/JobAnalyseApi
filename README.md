BASE_URL = 'http://www.d3collection.cn:5020/'
# JobApi
## 首页
### 获取所有的工作分类

接口地址：`/api/getAllJobCategory`
返回值：

```Json
{
    data: [
        {
            job: [
                {
                    jobId: "343", 
                    jobName: "MySQL"
                }, 
                {
                    jobId: "344", 
                    jobName: "SQLServer"
                }, 
                {
                    jobId: "345", 
                    jobName: "Oracle"
                }, 
                {
                    jobId: "346", 
                    jobName: "DB2"
                }, 
                {
                    jobId: "347", 
                    jobName: "MongoDB"
                }, 
                {
                    jobId: "348", 
                    jobName: "ETL"
                }, 
                {
                    jobId: "349", 
                    jobName: "Hive"
                }, 
                {
                    jobId: "350", 
                    jobName: "数据仓库"
                }, 
                {
                    jobId: "351", 
                    jobName: "DBA其它"
                }
            ], 
            categoryName: "DBA"
        }, 
        {
            job: [
                {
                    jobId: "335", 
                    jobName: "深度学习"
                }, 
                {
                    jobId: "336", 
                    jobName: "机器学习"
                }, 
                {
                    jobId: "337", 
                    jobName: "图像处理"
                }, 
                {
                    jobId: "338", 
                    jobName: "图像识别"
                }, 
                {
                    jobId: "339", 
                    jobName: "语音识别"
                }, 
                {
                    jobId: "340", 
                    jobName: "机器视觉"
                }, 
                {
                    jobId: "341", 
                    jobName: "算法工程师"
                }, 
                {
                    jobId: "342", 
                    jobName: "自然语言处理"
                }
            ], 
            categoryName: "人工智能"
        }  
    ]
}
```
 
### 获取城市职位信息列表


接口地址：`/api/getCityJobInfoList/<str:area>/<int:category_id>/<int:pn>`
例：`/api/getCityJobInfoList/北京/286/1`
返回值：

```Json
{
    data: [
        {
            workInfo: "海淀区 3-5年", 
            salary: "25k-35k", 
            companyInfo: "C轮 | 2000人以上 | 移动互联网,数据服务", 
            positionName: "Android开发工程师", 
            district: "海淀区", 
            createTime: "05月01日", 
            companyLogoUrl: "www.lgstatic.com/thumbnail_120x120/i/image/M00/8A/E2/CgpEMlrUDpCAa0PVAAUIaNb-8lc161.png", 
            positionId: "3515839", 
            companyName: "字节跳动"
        }, 
        {
            workInfo: "朝阳区 3-5年", 
            salary: "12k-24k", 
            companyInfo: "天使轮 | 15-50人 | 移动互联网,其他", 
            positionName: "高级安卓android开发", 
            district: "朝阳区", 
            createTime: "05月01日", 
            companyLogoUrl: "www.lgstatic.com/thumbnail_120x120/i/image/M00/C3/80/Cgp3O1jb4KqAftY0AAXjXpp53W8337.jpg", 
            positionId: "4503252", 
            companyName: "北京新城未来文化传媒有限公司"
        }, 
        {
            workInfo: "朝阳区 3-5年", 
            salary: "30k-55k", 
            companyInfo: "D轮及以上 | 500-2000人 | 移动互联网,文化娱乐", 
            positionName: "Android研发", 
            district: "朝阳区", 
            createTime: "05月01日", 
            companyLogoUrl: "www.lgstatic.com/thumbnail_120x120/i/image/M00/22/61/Cgp3O1cUq6yAMA-_AAAOM7mNTQc202.jpg", 
            positionId: "4279960", 
            companyName: "一下科技"
        }
    ]
}
```


### 搜索公司

接口地址：`/api/searchCompany/<str:area>/<int:category_id>/<str:text>`
例：`/api/searchCompany/北京/286/一下`
返回值：


```Json
{
    data: [
        {
            positionName: "Android开发工程师", 
            positionId: "4069396", 
            companyLogoUrl: "www.lgstatic.com/thumbnail_120x120/i/image/M00/22/61/Cgp3O1cUq6yAMA-_AAAOM7mNTQc202.jpg", 
            salary: "20k-35k", 
            companyInfo: "D轮及以上 | 500-2000人 | 移动互联网,文化娱乐", 
            companyName: "一下科技", 
            createTime: "04月18日", 
            district: "朝阳区", 
            workInfo: "朝阳区 3-5年"
        }, 
        {
            positionName: "音视频SDK开发工程师(Android端）", 
            positionId: "4327269", 
            companyLogoUrl: "www.lgstatic.com/thumbnail_120x120/i/image/M00/22/61/Cgp3O1cUq6yAMA-_AAAOM7mNTQc202.jpg", 
            salary: "20k-40k", 
            companyInfo: "D轮及以上 | 500-2000人 | 移动互联网,文化娱乐", 
            companyName: "一下科技", 
            createTime: "04月18日", 
            district: "朝阳区", 
            workInfo: "朝阳区 3-5年"
        }
    ]
}
```

## 工作分析
### 获取工资分布

接口地址：`/api/getSalaryDistributing/<str:area>/<int:category_id>`
例：`/api/getSalaryDistributing/北京/286`
返回值：

```Json
{
    data: {
        value: [
            971, 
            295, 
            158
        ], 
        text: [
            "25K及以下", 
            "26K-30K", 
            "31K+"
        ]
    }
}
```


### 获取近一周工资曲线

接口地址：`/api/getSalaryWeekGraph/<str:area>/<int:category_id>`
例：`/api/getSalaryWeekGraph/北京/286`
返回值：

```Json
{
	"data": {
		"text": ["05-15", "05-16", "05-17", "05-18"],
		"multiLineValue": [{
			"text": "平均工资",
			"value": [19, 21, 19, 20]
		}, {
			"text": "最高工资",
			"value": [37, 42, 40, 37]
		}, {
			"text": "最低工资",
			"value": [2, 6, 7, 11]
		}]
	}
}
```


### 获取近一周工资TOP10

接口地址：`/api/getSalaryTop10/<str:area>/<int:category_id>`
例：`/api/getSalaryTop10/北京/286`
返回值：

```Json
{
    data: [
        {
            companyName: "iHandy", 
            salary: "30k-60k"
        }, 
        {
            companyName: "Momenta", 
            salary: "30k-60k"
        }, 
        {
            companyName: "搜狗", 
            salary: "30k-60k"
        }, 
        {
            companyName: "一下科技", 
            salary: "30k-55k"
        }, 
        {
            companyName: "小米", 
            salary: "30k-50k"
        }, 
        {
            companyName: "美团点评", 
            salary: "30k-50k"
        }, 
        {
            companyName: "陌陌", 
            salary: "28k-50k"
        }, 
        {
            companyName: "陌陌", 
            salary: "28k-50k"
        }, 
        {
            companyName: "字节跳动", 
            salary: "25k-50k"
        }, 
        {
            companyName: "字节跳动", 
            salary: "25k-50k"
        }
    ]
}
```


### 获取区域工作数量分布
接口地址：`/api/getDistrictJobDistributing/<str:city>/<int:category_id>`
例：`/api/getDistrictJobDistributing/北京/286`
返回值：

```Json
{
	"data": {
		"value": [803, 837, 258],
		"text": ["朝阳区", "海淀区", "其他区"]
	}
}
```



### 获取区域工资平均数
接口地址：`/api/getDistrictSalaryAvg/<str:city>/<int:category_id>`
例：`/api/getDistrictSalaryAvg/北京/286`
返回值：

```Json
{
	"data": {
		"value": [22, 22, "15"],
		"text": ["朝阳区", "海淀区", "其他区"]
	}
}
```



### 获取工作年限的分布情况
接口地址：`/api/getWorkYearDistributing/<str:city>/<int:category_id>`
例：`/api/getWorkYearDistributing/北京/286`
返回值：

```Json
{
	"data": {
		"value": [436, 2, 15, 1073, 230, 116, 55],
		"text": ["1-3年", "10年以上", "1年以下", "3-5年", "5-10年", "不限", "应届毕业生"]
	}
}
```



### 获取工作时间和工作数量走向图
接口地址：`/api/getWorkYearGraph/<str:city>/<int:category_id>`
例：`/api/getWorkYearGraph/北京/286`
返回值：

```Json
{
	"data": {
		"multiLineValue": [{
			"text": "18-04",
			"value": [306, 1, 12, 797, 163, 93, 48]
		}, {
			"text": "18-05",
			"value": [130, 1, 3, 276, 67, 23, 7]
		}],
		"text": ["1-3年", "10年以上", "1年以下", "3-5年", "5-10年", "不限", "应届毕业生"]
	}
}
```


### 获取融资情况
接口地址：`/api/getFinanceStageDistributing/<str:city>/<int:category_id>`
例：`/api/getFinanceStageDistributing/北京/286`
返回值：

```Json
{
	"data": {
		"value": [246, 256, 215, 243, 284, 417, 103, 161],
		"text": ["A轮", "B轮", "C轮", "D轮及以上", "上市公司", "不需要融资", "天使轮", "未融资"]
	}
}
```



### 获取融资情况所对应的工资情况
接口地址：`getSalaryByFinanceStage/<str:city>/<int:category_id>`
例：`getSalaryByFinanceStage/北京/286`
返回值：

```Json
{
	"data": {
		"value": [19, 22, 25, 27, 22, 20, 17, 16],
		"text": ["A轮", "B轮", "C轮", "D轮及以上", "上市公司", "不需要融资", "天使轮", "未融资"]
	}
}
```


