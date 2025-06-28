Hello everyone, welcome back to the special session on HarmonyOS 5 Meichuang chart components. In this episode, we will explain the detailed usage of the legend properties in the McLineChart line chart component.  


## Overview of legend Properties  
The legend is a vital component in line charts, used to display identifiers and names of different series and support interactive operations. Meichuang Charts provides rich legend configuration options, allowing flexible control over the display style, position, and behavior of the legend.  


## Property Details  

### 1. `show` Property  
**Function**: Controls whether the legend component is displayed.  
**Type**: Boolean  
**Default**: `true`  
**Options**:  
- `true`: Display the legend.  
- `false`: Hide the legend.  
**Scenario**: Set to `false` when the legend needs to be hidden, suitable for cases where chart space is limited or series names are already clearly marked in the chart.  
**Code Example**:  
```typescript
legend: {
  show: false  // Hide the legend
}
```  

### 2. `orient` Property  
**Function**: Sets the arrangement direction of the legend.  
**Type**: String  
**Default**: `'horizontal'`  
**Options**:  
- `'horizontal'`: Horizontal arrangement.  
- `'vertical'`: Vertical arrangement.  
**Scenario**: Vertical arrangement saves horizontal space when there are many series; horizontal arrangement aligns with conventional reading habits.  
**Code Example**:  
```typescript
legend: {
  orient: 'vertical'  // Arrange legend vertically
}
```  

### 3. Position Properties (`left/right/top/bottom`)  
**Function**: Controls the position of the legend in the chart.  
**Type**: String|Number  
**Defaults**:  
- `left: 'auto'`  
- `right: 'auto'`  
- `top: '6%'`  
- `bottom: 'auto'`  
**Options**:  
- Pixel values (e.g., `10`).  
- Percentages (e.g., `'10%'`).  
- `'auto'`: Automatic positioning.  
**Scenario**: Use to precisely control the legend position when automatic positioning is insufficient.  
**Code Example**:  
```typescript
legend: {
  left: 'center',  // Horizontally centered
  top: 'top'       // Aligned to the top
}
```  

### 4. `icon` Property  
**Function**: Sets the icon shape of legend items.  
**Type**: String  
**Default**: `'roundRect'`  
**Options**:  
- `'rect'`: Rectangle.  
- `'circle'`: Circle.  
- `'roundRect'`: Rounded rectangle.  
**Scenario**: Choose different icon shapes based on design requirements; rounded rectangles are the default recommended style.  
**Code Example**:  
```typescript
legend: {
  icon: 'circle'  // Use circular icons
}
```  

### 5. `iconRadian` Property  
**Function**: Sets the corner radius of rounded rectangles (only valid when `icon` is `'roundRect'`).  
**Type**: Number  
**Default**: `2`  
**Scenario**: Adjust the corner size of legend icons for different visual effects.  
**Code Example**:  
```typescript
legend: {
  icon: 'roundRect',
  iconRadian: 5  // Larger corner radius
}
```  

### 6. `itemGap` Property  
**Function**: Sets the interval between legend items.  
**Type**: Number  
**Default**: `10`  
**Scenario**: Adjust the interval for a more reasonable layout when there are many or few legend items.  
**Code Example**:  
```typescript
legend: {
  itemGap: 20  // Larger interval
}
```  

### 7. `itemTextGap` Property  
**Function**: Sets the interval between legend icons and text.  
**Type**: Number  
**Default**: `5`  
**Scenario**: Adjust the distance between icons and text to improve readability.  
**Code Example**:  
```typescript
legend: {
  itemTextGap: 10  // Larger icon-text interval
}
```  

### 8. `align` Property  
**Function**: Sets the alignment of legend markers and text.  
**Type**: String  
**Default**: `'auto'`  
**Options**:  
- `'auto'`: Automatic judgment.  
- `'left'`: Left alignment.  
- `'right'`: Right alignment.  
**Scenario**: Manually specify the alignment when automatic alignment is inadequate.  
**Code Example**:  
```typescript
legend: {
  align: 'right'  // Force right alignment
}
```  

### 9. `itemWidth/itemHeight` Properties  
**Function**: Sets the width and height of legend icons.  
**Type**: Number  
**Defaults**:  
- `itemWidth: 8`  
- `itemHeight: 8`  
**Scenario**: Adjust legend icon size to coordinate with the overall design.  
**Code Example**:  
```typescript
legend: {
  itemWidth: 12,
  itemHeight: 12  // Larger icons
}
```  

### 10. `selectAble` Property  
**Function**: Sets whether legend items can be selected.  
**Type**: Boolean  
**Default**: `true`  
**Scenario**: Disable selection when legend interaction is unnecessary.  
**Code Example**:  
```typescript
legend: {
  selectAble: false  // Disable legend selection
}
```  

### 11. `data` Property  
**Function**: Customizes legend data.  
**Type**: Array  
**Default**: `[]`  
**Scenario**: Use when customizing legend content instead of using series names.  
**Code Example**:  
```typescript
legend: {
  data: ['Custom Legend 1', 'Custom Legend 2']
}
```  

### 12. `textStyle` Property  
**Function**: Sets the text style of the legend.  
**Type**: Object  
**Default**:  
```typescript
{
  fontFamily: 'sans-serif',
  fontWeight: 'normal',
  fontSize: 30,
  color: '#333',
  formatter: null
}
```  
**Sub-property Details**:  

#### 12.1 `fontFamily`  
- **Function**: Font type.  
- **Type**: String.  
- **Default**: `'sans-serif'`.  

#### 12.2 `fontWeight`  
- **Function**: Font weight.  
- **Type**: String.  
- **Default**: `'normal'`.  

#### 12.3 `fontSize`  
- **Function**: Font size.  
- **Type**: Number.  
- **Default**: `30`.  

#### 12.4 `color`  
- **Function**: Font color.  
- **Type**: String.  
- **Default**: `'#333'`.  

#### 12.5 `formatter`  
- **Function**: Text formatting.  
- **Type**: String|Function.  
- **Default**: `null`.  
- **Examples**:  
  ```typescript
  formatter: '{value}件'  // Static text
  formatter: (name, index) => `${name}(${index})`  // Dynamic text
  ```  

**Code Example**:  
```typescript
legend: {
  textStyle: {
    fontSize: 24,
    color: '#666',
    formatter: '{value}数据'
  }
}
```  

### 13. `iconStyle` Property  
**Function**: Sets the style of legend icons.  
**Type**: Object  
**Default**: `{}`  
**Scenario**: Customize legend icon styles, such as color and border.  
**Code Example**:  
```typescript
legend: {
  iconStyle: {
    color: '#c23531',
    borderColor: '#444',
    borderWidth: 1
  }
}
```  

### 14. `textUnselectedStyle` Property  
**Function**: Sets the text style for unselected states.  
**Type**: Object  
**Default**:  
```typescript
{
  fontFamily: 'sans-serif',
  fontSize: 30,
  color: '#999'
}
```  
**Scenario**: Customize the text style of unselected legend items.  
**Code Example**:  
```typescript
legend: {
  textUnselectedStyle: {
    color: '#ccc',
    fontSize: 24
  }
}
```  

### 15. `iconUnselectedStyle` Property  
**Function**: Sets the icon style for unselected states.  
**Type**: Object  
**Default**:  
```typescript
{
  color: '#999'
}
```  
**Scenario**: Customize the icon style of unselected legend items.  
**Code Example**:  
```typescript
legend: {
  iconUnselectedStyle: {
    color: '#eee',
    opacity: 0.6
  }
}
```  

### 16. `rLevel` Property  
**Function**: Sets the legend rendering level.  
**Type**: Number  
**Default**: `20`  
**Scenario**: Adjust the stacking order of the legend with other elements.  
**Code Example**:  
```typescript
legend: {
  rLevel: 30  // Higher priority
}
```  

### 17. `animationCurve` Property  
**Function**: Sets the legend animation curve.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Scenario**: Customize the animation effect during legend interaction.  
**Code Example**:  
```typescript
legend: {
  animationCurve: 'linear'  // Linear animation
}
```  

### 18. `animationFrame` Property  
**Function**: Sets the legend animation frame rate.  
**Type**: Number  
**Default**: `0`  
**Scenario**: Control animation smoothness; larger values make animations smoother but consume more performance.  
**Code Example**:  
```typescript
legend: {
  animationFrame: 30  // Smoother animation
}
```  


## Complete Code Example  
The following is a comprehensive example of using legend properties:  

```typescript
import { McLineChart, Options } from '@mcui/mccharts'

@Entry
@Component
struct Index {
    @State maxData: number[] = [11, 11, 15, 13, 12, 130, 10]
    @State minData: number[] = [1, -20, 2, 5, 3, 2, 0]
    @State avgData: number[] = [6, -4, 8, 9, 7, 66, 5]
    
    @State seriesOption: Options = new Options({
      xAxis: {
        data: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
      },
      yAxis: {
        name: 'Temperature (°C)'
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
          color: 'auto',  // Automatically use series color
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
          name: 'Maximum Temperature',
          data: this.maxData,
          color: '#c23531'
        },
        {
          name: 'Minimum Temperature',
          data: this.minData,
          color: '#2f4554'
        },
        {
          name: 'Average Temperature',
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
                name: 'Maximum Temperature',
                data: this.maxData
              },
              {
                name: 'Minimum Temperature',
                data: this.minData
              },
              {
                name: 'Average Temperature',
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


## Practical Application Scenarios  
In real projects, legend configuration typically considers the following factors:  

1. **Responsive design**: Adjust legend position and direction based on screen size.  
2. **Brand consistency**: Use brand colors and fonts.  
3. **Accessibility**: Ensure sufficient contrast and font size.  
4. **Interactive experience**: Clearly distinguish selected/unselected states.  

For example, in a weather forecast app, optimize the legend as follows:  

```typescript
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
        '最高气温': 'Max',
        '最低气温': 'Min',
        '平均气温': 'Avg'
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

This configuration achieves:  
- Concise legend text (`Max/Min/Avg`).  
- Circular icons align with meteorological data visualization habits.  
- Bottom-center layout saves space.  
- Unselected states are noticeable but not obtrusive.  


This concludes this episode. We hope this article helps you fully master the usage of legend properties in Meichuang Charts' line charts, enabling you to flexibly create beautiful and practical data visualizations in real projects. If you have any questions, feel free to leave a comment!
