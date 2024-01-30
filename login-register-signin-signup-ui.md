# Login / Register / Signin / Signup UI

### 1. Login page

```javascript
import React from 'react'

const LoginPage = () => {
  return (
    <div className='page'>
      <div className='form_container'> 
      <h1>로그인</h1>
      <SignIn/>
      <p><Link to ={"/register"}>회원가입</Link></p>
      </div>
    </div>
  )
}

export default LoginPage
```

### 2. Signin page

<pre class="language-javascript"><code class="lang-javascript"><strong>// form 미설정
</strong><strong>import React from 'react'
</strong>
function Signin() {
  return (
    &#x3C;Form title={"로그인"} />
  )
}

export default Signin
</code></pre>

### 3. Signup page

```javascript
// form 미설정
import React from 'react'

function Signup() {
  return (
    <Form title={"가입하기"} />
  )
}

export default Signup

```
