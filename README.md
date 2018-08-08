# QiButton_EventInterval
控制UIButton的点击间隔时间的方法

### 思路简介
1、创建一个UIButton的类别，使用runtime为UIButton增加public属性qi_eventInterval和private属性eventUnavailable。<br/>
2、在+load方法中使用runtime将UIButton的-sendAction:to:forEvent:方法与自定义的-qi_sendAction:to:forEvent:方法交换Implementation。<br/>
3、使用qi_eventInterval作为控制eventUnavailable的计时因子，用eventUnavailable开控制UIButton的event事件是否有效。<br/>

### 使用方法
```01
UIButton *button = [UIButton buttonWithType:UIButtonTypeSystem];
/* here is some button's configuration codes */
[self.view addSubview:button];
    
//! 设置按钮的点击响应间隔时间
button.qi_eventInterval = 2.0;
```

### 实现效果
![01](/Source/QiButton_EventInterval_01.gif)
