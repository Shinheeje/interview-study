#### **React.lazy**

**React.lazy란?**

**▶ 동적 가져오기를 사용하여 구성 요소 수준에서 React에플리케이션을 쉽게 코드분할 할 수 있게 도와주는**

**매서드입니다.**

**React.lazy를 사용하는 이유** 

**큰 React 애플리케이션은** **필요할 때만 애플리케이션의 다른 부분을 로드하려고 노력하지 않으면**

**사용자가 첫 페이지를 로드하는 즉시**

**대규모 단일 javascript 번들이 사용자에게 전송됩니다.**

**이는 페이지 성능에 상당한 영향을 줄 수 있습니다.**

```
(App.js)
import {lazy, Suspense, useEffect, useState} from 'react'

const Detail = lazy( () => import('./routes/Detail.js') )
const Cart = lazy( () => import('./routes/Cart.js') )
```

**쉽게 말 하면 Detail 컴포넌트가 필요해지면 import 해주세요 라는 뜻입니다.**

**이렇게 해놓으면 Detail 컴포넌트 내용을 다른 js 파일로 쪼개줍니다.**

**React.lazy 단점**

**▶ 초기 로딩 시 약간의 딜레이가 발생할 수 있습니다.  
React.lazy() 함수를 사용하면, 초기 로딩 시 약간의 딜레이가 발생할 수 있습니다. 이는 지연 로딩된 컴포넌트를 필요할 때 동적으로 로드하기 때문입니다. 그러나 이러한 딜레이는 컴포넌트 크기와 네트워크 속도에 따라 다르며, 보통은 미미한 수준입니다.**

#### **Suspense**

**Suspense는 React의 비동기적인 UI 처리를 돕는 기능 중 하나입니다. Suspense는 리액트가 특정 컴포넌트의 데이터나 리소스가 로드될 때까지 기다리도록 하여, 로딩 상태를 표시할 수 있게 해줍니다.**  
  
**보통 Suspense는 React.lazy()와 함께 사용되어 코드 스플리팅을 통해 컴포넌트 로딩을 최적화하는 데 사용됩니다. React.lazy()는 코드 스플리팅을 통해 컴포넌트를 비동기적으로 로딩하는 방식을 사용합니다. 하지만, 이를 위해 Suspense를 사용하여 코드 스플리팅된 컴포넌트가 로딩될 때까지 로딩 중인 UI를 표시할 수 있습니다.**  
  
**Suspense 컴포넌트는 fallback prop을 포함하고 있습니다. fallback prop은 로딩 중인 UI를 나타내는 React 엘리먼트를 포함합니다. 예를 들어, 로딩 중인 UI를 나타내는 스피너나 로딩 바 등을 fallback prop에 포함할 수 있습니다.**  
  
**Suspense를 사용하면, 비동기적인 로딩이 필요한 부분에서 코드 스플리팅을 사용하여 앱의 성능을 최적화할 수 있습니다.**

```
<Suspense fallback={ <div>로딩중임</div> }>
  <Detail shoes={shoes} />
</Suspense>
```
