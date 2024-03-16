# Chat GPT API 사용하기

### 1. 호출

* 공식문서에서 제공하는 포맷을 통해 요청을 보내면 된다.

```jsx
export const CallAPI = async () => {

//     curl https://api.openai.com/v1/chat/completions \
//   -H "Content-Type: application/json" \
//   -H "Authorization: Bearer $OPENAI_API_KEY" \
//   -d '{
//      "model": "gpt-3.5-turbo",
//      "messages": [{"role": "user", "content": "Say this is a test!"}],
//      "temperature": 0.7
//    }'

const response = await fetch("https://api.openai.com/v1/chat/completions", {
    method : "POST",
    headers: {
        "Content-Type" : "application/json",
        "Authorization" : `Bearer ${import.meta.env.VITE_GPT_API_KEY}`,
    },
    body : JSON.stringify({
        model : "gpt-3.5-turbo",
        messages : [{role: "user", content: "Say this is a test!"}],
        temperature : 0.7,
        max_tokens : 1_000,
    }),
});
const responseData = await response.json();
console.log("응답 데이터", responseData);

const message = responseData.choices[0].message.content;

return message;
}
```

### 2. 연동
