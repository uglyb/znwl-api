#### <span id="drill-module">设备payload定义</span>
!> 设备payload使用json格式传输 


##### payload定义


> ###### PM2.5传感器 0301

```json
{
    level:"1",  //1-5
    desc:"空气优",
    value:"20",
    history:[ //返回7天
        {
            date:"10-20",
            value:"50"
        },
        {
            date:"10-21",
            value:"42"
        }
    ]
} 
```


> ###### CO2传感器 0302

```json
{
    level:"1",  //1-5
    desc:"含量正常",
    value:"50",
    history:[ //返回7天
        {
            date:"10-20",
            value:"50"
        },
        {
            date:"10-21",
            value:"42"
        }
    ]
} 

```

> ###### 温湿度传感器 3001

```json
{
   level:"1", //1-5
   summary:"偏热",
   desc:"注意防暑降温",
   tValue:"27.5",   //温度
   hValue:"30",     //湿度
   iValue:"599",    //光照度
   temperature:[
    {
        date:"2017-10-20 08:20",
        value:"20"
    },
    {
        date:"2017-10-20 12:00",
        value:"25"
    },
    {
        date:"2017-10-20 18:34",
        value:"21"
    },
    {
        date:"2017-10-21 08:20",
        value:"20"
    },
    {
        date:"2017-10-21 12:00",
        value:"25"
    },
    {
        date:"2017-10-21 18:34",
        value:"21"
    }
   ],
   humidity:[
    {
        date:"2017-10-20 08:20",
        value:"20"
    },
    {
        date:"2017-10-20 12:00",
        value:"25"
    },
    {
        date:"2017-10-20 18:34",
        value:"21"
    },
    {
        date:"2017-10-21 08:20",
        value:"20"
    },
    {
        date:"2017-10-21 12:00",
        value:"25"
    },
    {
        date:"2017-10-21 18:34",
        value:"21"
    }
   ]
}

```

> ###### 烟雾探测器 0307

```json
//返回7天
[
    {
        date:"2018-03-20 18:00",
        value:"正常工作"
    },
    {
        date:"2018-03-20 20:00",
        value:"正常工作"
    }
    {
        date:"2018-03-20 00:00",
        value:"触发警报"
    }
    {
        date:"2018-03-20 05:00",
        value:"正常工作"
    }
]

```

> ###### 窗磁 5003

```json
//返回7天
[
    {
        date:"2018-03-20 18:00",
        value:"窗户打开"
    },
    {
        date:"2018-03-20 20:00",
        value:"窗户关闭"
    }
    {
        date:"2018-03-20 00:00",
        value:"窗户打开"
    }
    {
        date:"2018-03-20 05:00",
        value:"窗户关闭"
    }
]

```

---