# CSS Animation

### Step1 : 建立 @keyframe
##### 結構 from to
```
/* 使用 `@keyframes` 定義，後面包含其自訂名稱 */
@keyframes rotate-keyframe {
  /* 定義每個階段的影格變化  */
  from {
    /* 定義元素在該影格所套用的樣式 */
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```
##### 結構 0% -> 100%
```
@keyframes rotate-keyframe {
  /* 定義每個階段的影格變化  */
  0% {
    /* 定義元素在該影格所套用的樣式 */
    transform: rotate(0deg);
  }
  50% {
    transform: rotate(180deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
```

### Step2 : 套用 animation 並載入影格
至少要包含兩個屬性才能運作 - animation-name(@keyframes 名稱)、animation-duration (動畫持續時間)

---
## Animation 屬性
| 屬性                      | 說明                    |
| -----------------         |:----------------------- |
| animation-name            | keyframes 名稱   |
| animation-duration        | 決定動畫演時間長短     |
| animation-iteration-count | 動畫播放次數，可以填入數值（整數，或是包含小數點均可），或者可以使用 infinite 表示無限次重複播放。     |
| animation-timing-function | 動畫效果轉換     |
| animation-direction       | 動畫播放方向     |
| animation-delay       | 第一次播放動畫時所延遲的時間     |

##### animation-timing-function :動畫效果轉換
```
animation-timing-function: ease;
animation-timing-function: ease-in;
animation-timing-function: ease-out;
animation-timing-function: linear;        /* 線性的速率 */
animation-timing-function: steps(5, end); /* 階段性的轉換 */
animation-timing-function: cubic-bezier(.4,.94,.56,1.59); /* 自訂義貝茲轉換速率 */
```

##### animation-direction :動畫播放方向
```
animation-direction: normal;             /* 正向播放 */
animation-direction: reverse;            /* 反向播放 */
animation-direction: alternate;          /* 單數次為正向播放，雙數次為反向播放 */
animation-direction: alternate-revers;   /* 與前者相反，雙數次為正向播放，單數次為反向播放 */
```

---
## Transition 屬性
> 用於補足hover 或 toggle class 之間的動畫 [color=#3b75c6]

| 屬性                      | 說明                    |
| -----------------         |:----------------------- |
| transition-property       | 指定要轉換的CSS屬性   |
| transition-duration       | 轉換需要的時間，預設0，單位為s或ms     |
| transition-delay          | 延遲多久轉換，預設0，單位為s或ms     |
| transition-timing-function| 轉換時的速度曲線，預設ease     |

## Transform
- 縮放比例 Scale ,ScaleX, ScaleY
- 旋轉 rotate
- 平移 translate , translateX, translateY
- 傾斜 skew
- 基準點 transition-origin

---
## 比較
| 動畫型態            | 說明                    |
| -----------------  |:----------------------- |
| Animation       | 細節複雜的動畫效果，強調CSS屬性的流程與控制，可加keyframes / CSS屬性變化   |
| Transition      | 基礎的動畫效果，強調CSS屬性的過渡動畫 / CSS屬性變化     |
| Transform       | 控制html元素的旋轉、縮放、移動等等 / HTML元素(包含內容)變化 / 因會操作HTML元素運算，因此必須考慮效能     |

==Translaste : 只是transform的一個函數==

## 結論
* animation可以說是包含很多個transition控制的屬性，transition是大略的CSS屬性變化，animation可以做出更細節的部分
* transform可以在animation中當作屬性被運用
* animation和transform可直接運行原因為都有指定屬性“值”的變換，而transition沒有
