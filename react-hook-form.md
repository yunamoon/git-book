# react-hook-form

### 1. react-hooks-form?

[공식문서](https://www.react-hook-form.com/)

[참고문서](https://tech.inflab.com/202207-rallit-form-refactoring/react-hook-form/)

* react-hook-form은 React 기반의 폼 관리 라이브러리, 복잡한 폼을 간단하게 처리하고 상태 관리를 용이하게 해주는 도구
* 최소한의 코드로 많은 기능을 구현 할 수 있음

### 2. recat-hook-form으로 유효성 체크하기

```vim
npm install react-hook-form
```

<pre class="language-javascript"><code class="lang-javascript"><strong>/**  useForm import */
</strong><strong>import { useForm } from 'react-hook-form';
</strong><strong>
</strong> const { register, handleSubmit , formState : {errors} , reset} = useForm({
    mode : 'onChange'
  });
</code></pre>

* 사용하는 generic props: register, handleSubmit , formState : {errors} , reset&#x20;
* &#x20;상세한 설명은 공식 문서 참고&#x20;
* [https://react-hook-form.com/docs/useform](https://react-hook-form.com/docs/useform)
* mode는 onChange input box 내 변경 사항이 있으면 유효성 체크&#x20;

### 3. ID 유효성 체크

```jsx

  //form 양식
  
  <form onSubmit={handleSubmit(onSubmit)} className={styles.form}>
      <div>
        <input
        type="email"
        placeholder="E-mail" 
        {...register("email" , userEmail)}
        />
        {errors?.email && 
        <div>
          <span className={styles.form_error}>
            {errors.email.message}
          </span>
        </div>
           }
     </div>
   <form>
   
```

* register로 등록 받고, userEmail 객체로 관리&#x20;
* 유효성 체크 시 오류가 발생하면 formState에 저장되는데 errors로 반환되는데, 이때 errors.message를 반환

```jsx
// ID 유효성 검사 양식


const userEmail = {
    required: '이메일을 입력해주세요.',
     pattern: {
      value: /^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/,
      message: '입력하신 이메일 주소가 올바르지 않습니다.',
    },
  }
```

### 4. Password 유효성 체크

```jsx
// form 양식

 <form onSubmit={handleSubmit(onSubmit)} className={styles.form}>
        <div>
        <input
        type="password"
        placeholder="Password"
        {...register("password" , userPassword)} />
        {errors?.password &&
        <div>
          <span className={styles.form_error}>
          {errors.password.message}
          </span>
        </div>
        }
      </div>
      <button type='submit'>{title}</button>
      <span className={styles.form_error}></span>
    </form>
```

* register로 등록 받고, userPassword 객체로 관리&#x20;
* 유효성 체크 시 오류가 발생하면 formState에 저장되는데 errors로 반환되는데, 이때 errors.message를 반환

```jsx
// password 유효성 검사 양식

 const userPassword = {
    required: '비밀번호를 입력해주세요.',
    minLength: {
      value: 10,
      message: '비밀번호는 최소 10자 이상이어야 합니다.',
    },
    pattern: {
      value: /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{10,}$/,
      message: '영어 대문자, 소문자, 숫자, 특수문자 중 2종류 문자 조합이어야 합니다.',
    }
  };
```

