大家好，欢迎回来鸿蒙5莓创图表组件的专场，我们这一期来讲解McLineChart折线图组件的legend图例属性的详细用法。

## legend属性概述
legend是折线图中非常重要的组件，用于展示不同系列的标识和名称，并支持交互操作。莓创图表提供了丰富的legend配置选项，让我们可以灵活控制图例的显示样式、位置和行为。

## 属性详解
### 1. show属性
**作用**：控制是否显示图例组件

**类型**：Boolean

**默认值**：true

**可选值**：

+ true：显示图例
+ false：隐藏图例

**场景**：当需要隐藏图例时设置为false，适用于图表空间有限或系列名称在图表中已经明确标注的情况。

**代码示例**：

```plain
legend: {
  show: false  // 隐藏图例
}
```

### 2. orient属性
**作用**：设置图例的排列方向

**类型**：String

**默认值**：'horizontal'

**可选值**：

+ 'horizontal'：水平排列
+ 'vertical'：垂直排列

**场景**：当系列较多时，垂直排列可以节省水平空间；水平排列则更符合常规阅读习惯。

**代码示例**：

```plain
legend: {
  orient: 'vertical'  // 垂直排列图例
}
```

### 3. 位置属性（left/right/top/bottom）
**作用**：控制图例在图表中的位置

**类型**：String|Number

**默认值**：

+ left: 'auto'
+ right: 'auto'
+ top: '6%'
+ bottom: 'auto'

**可选值**：

+ 像素值：如10
+ 百分比：如'10%'
+ 'auto'：自动定位

**场景**：当需要精确控制图例位置时使用，特别是当自动定位不符合需求时。

**代码示例**：

```plain
legend: {
  left: 'center',  // 水平居中
  top: 'top'       // 顶部对齐
}
```

### 4. icon属性
**作用**：设置图例项的图标形状

**类型**：String

**默认值**：'roundRect'

**可选值**：

+ 'rect'：矩形
+ 'circle'：圆形
+ 'roundRect'：圆角矩形

**场景**：根据设计需求选择不同的图标形状，圆角矩形是默认推荐样式。

**代码示例**：

```plain
legend: {
  icon: 'circle'  // 使用圆形图标
}
```

### 5. iconRadian属性
**作用**：设置圆角矩形的圆角半径（仅当icon为'roundRect'时有效）

**类型**：Number

**默认值**：2

**场景**：调整图例图标的圆角大小，实现不同的视觉效果。

**代码示例**：

```plain
legend: {
  icon: 'roundRect',
  iconRadian: 5  // 更大的圆角
}
```

### 6. itemGap属性
**作用**：设置图例项之间的间隔

**类型**：Number

**默认值**：10

**场景**：当图例项较多或较少时，调整间隔可以使布局更合理。

**代码示例**：

```plain
legend: {
  itemGap: 20  // 更大的间隔
}
```

### 7. itemTextGap属性
**作用**：设置图例图标和文本之间的间隔

**类型**：Number

**默认值**：5

**场景**：调整图标和文本的距离，改善可读性。

**代码示例**：

```plain
legend: {
  itemTextGap: 10  // 更大的图标文本间隔
}
```

### 8. align属性
**作用**：设置图例标记和文本的对齐方式

**类型**：String

**默认值**：'auto'

**可选值**：

+ 'auto'：自动判断
+ 'left'：左对齐
+ 'right'：右对齐

**场景**：当自动对齐不符合需求时，手动指定对齐方式。

**代码示例**：

```plain
legend: {
  align: 'right'  // 强制右对齐
}
```

### 9. itemWidth/itemHeight属性
**作用**：设置图例图标的宽度和高度

**类型**：Number

**默认值**：

+ itemWidth: 8
+ itemHeight: 8

**场景**：调整图例图标的大小，使其与整体设计协调。

**代码示例**：

```plain
legend: {
  itemWidth: 12,
  itemHeight: 12  // 更大的图标
}
```

### 10. selectAble属性
**作用**：设置图例项是否可以被选中

**类型**：Boolean

**默认值**：true

**场景**：当不需要图例交互功能时，可以禁用选择功能。

**代码示例**：

```plain
legend: {
  selectAble: false  // 禁用图例选择
}
```

### 11. data属性
**作用**：自定义图例数据

**类型**：Array

**默认值**：[]

**场景**：当需要自定义图例内容而非使用系列名称时使用。

**代码示例**：

```plain
legend: {
  data: ['自定义图例1', '自定义图例2']
}
```

### 12. textStyle属性
**作用**：设置图例文本样式

**类型**：Object

**默认值**：

```plain
{
  fontFamily: 'sans-serif',
  fontWeight: 'normal',
  fontSize: 30,
  color: '#333',
  formatter: null
}
```

**子属性详解**：

#### 12.1 fontFamily
**作用**：字体类型  
**类型**：String  
**默认值**：'sans-serif'

#### 12.2 fontWeight
**作用**：字体粗细  
**类型**：String  
**默认值**：'normal'

#### 12.3 fontSize
**作用**：字体大小  
**类型**：Number  
**默认值**：30

#### 12.4 color
**作用**：字体颜色  
**类型**：String  
**默认值**：'#333'

#### 12.5 formatter
**作用**：文本格式化  
**类型**：String|Function  
**默认值**：null  
**示例**：

```plain
formatter: '{value}件'  // 静态文本
formatter: (name, index) => `${name}(${index})`  // 动态文本
```

**代码示例**：

```plain
legend: {
  textStyle: {
    fontSize: 24,
    color: '#666',
    formatter: '{value}数据'
  }
}
```

### 13. iconStyle属性
**作用**：设置图例图标样式

**类型**：Object

**默认值**：{}

**场景**：自定义图例图标的样式，如颜色、边框等。

**代码示例**：

```plain
legend: {
  iconStyle: {
    color: '#c23531',
    borderColor: '#444',
    borderWidth: 1
  }
}
```

### 14. textUnselectedStyle属性
**作用**：设置未选中状态的文本样式

**类型**：Object

**默认值**：

```plain
{
  fontFamily: 'sans-serif',
  fontSize: 30,
  color: '#999'
}
```

**场景**：自定义未选中图例项的文本样式。

**代码示例**：

```plain
legend: {
  textUnselectedStyle: {
    color: '#ccc',
    fontSize: 24
  }
}
```

### 15. iconUnselectedStyle属性
**作用**：设置未选中状态的图标样式

**类型**：Object

**默认值**：

```plain
{
  color: '#999'
}
```

**场景**：自定义未选中图例项的图标样式。

**代码示例**：

```plain
legend: {
  iconUnselectedStyle: {
    color: '#eee',
    opacity: 0.6
  }
}
```

### 16. rLevel属性
**作用**：设置图例渲染级别

**类型**：Number

**默认值**：20

**场景**：当需要调整图例与其他元素的叠放顺序时使用。

**代码示例**：

```plain
legend: {
  rLevel: 30  // 更高优先级
}
```

### 17. animationCurve属性
**作用**：设置图例动画曲线

**类型**：String

**默认值**：'easeOutCubic'

**场景**：自定义图例交互时的动画效果。

**代码示例**：

```plain
legend: {
  animationCurve: 'linear'  // 线性动画
}
```

### 18. animationFrame属性
**作用**：设置图例动画帧数

**类型**：Number

**默认值**：0

**场景**：控制动画流畅度，值越大动画越流畅但性能消耗也越大。

**代码示例**：

```plain
legend: {
  animationFrame: 30  // 更流畅的动画
}
```

## 完整代码示例
下面是一个综合使用legend属性的完整示例：

```plain
import { McLineChart, Options } from '@mcui/mccharts'

@Entry
@Component
struct Index {
    @State maxData: number[] = [11, 11, 15, 13, 12, 130, 10]
    @State minData: number[] = [1, -20, 2, 5, 3, 2, 0]
    @State avgData: number[] = [6, -4, 8, 9, 7, 66, 5]
    
    @State seriesOption: Options = new Options({
      xAxis: {
        data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
      },
      yAxis: {
        name: '温度(℃)'
      },
      legend: {
        show: true,
        orient: 'horizontal',
        left: 'center',
        top: 'top',
        icon: 'roundRect',
        iconRadian: 4,
        itemGap: 15,
        itemTextGap: 8,
        itemWidth: 12,
        itemHeight: 12,
        textStyle: {
          fontSize: 24,
          color: '#333',
          formatter: '{value}温度'
        },
        iconStyle: {
          color: 'auto',  // 自动使用系列颜色
          borderColor: '#666',
          borderWidth: 1
        },
        textUnselectedStyle: {
          color: '#bbb',
          fontSize: 22
        },
        iconUnselectedStyle: {
          opacity: 0.5
        }
      },
      series: [
        {
          name: '最高气温',
          data: this.maxData,
          color: '#c23531'
        },
        {
          name: '最低气温',
          data: this.minData,
          color: '#2f4554'
        },
        {
          name: '平均气温',
          data: this.avgData,
          color: '#61a0a8'
        }
      ]
    })
    
    aboutToAppear() {
        setTimeout(() => {
          this.maxData = [110, 110, 150, 130, 120, 190, 100]
          this.minData = [-1, -2, -2, -5, 3, -2, 0]
          this.avgData = [55, 54, 74, 62, 61, 94, 50]
          
          this.seriesOption.setVal({
            series: [
              {
                name: '最高气温',
                data: this.maxData
              },
              {
                name: '最低气温',
                data: this.minData
              },
              {
                name: '平均气温',
                data: this.avgData
              }
            ]
          })
        }, 2000)
    }
    
    build() {
        Row() {
          McLineChart({
            options: this.seriesOption
          })
        }
        .height('50%')
    }
}
```

## 实际应用场景
在实际项目中，legend的配置通常需要考虑以下因素：

1. **响应式设计**：根据屏幕大小调整图例位置和方向
2. **品牌一致性**：使用品牌色和字体
3. **可访问性**：确保足够的对比度和字体大小
4. **交互体验**：合理的选中/未选中状态区分

例如，在天气预报应用中，我们可以这样优化图例：

```plain
legend: {
  orient: 'horizontal',
  left: 'center',
  bottom: 10,
  icon: 'circle',
  itemWidth: 10,
  itemHeight: 10,
  textStyle: {
    fontSize: 24,
    color: '#333',
    fontFamily: 'HarmonyOS Sans',
    formatter: (name) => {
      const map = {
        '最高气温': '最高',
        '最低气温': '最低',
        '平均气温': '平均'
      }
      return map[name] || name
    }
  },
  iconStyle: {
    borderWidth: 0
  },
  textUnselectedStyle: {
    color: '#999',
    opacity: 0.7
  }
}
```

这种配置实现了：

+ 简洁的图例文本（最高/最低/平均）
+ 圆形图标更符合气象数据的视觉习惯
+ 底部居中布局节省空间
+ 未选中状态明显但不过于突出

好，这期讲到这里就结束了，希望大家通过这篇文章能够全面掌握莓创图表折线图legend属性的使用方法，在实际项目中灵活运用，创建出既美观又实用的数据可视化图表。如果有任何问题，欢迎在评论区留言讨论。