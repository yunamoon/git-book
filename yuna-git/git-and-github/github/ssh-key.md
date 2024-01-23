# SSH key

### SSH

S**SSH**는 **Secure Shell**의 준말로, **비밀 키(Private Key)와 공개 키(Public Key) 한 쌍을 이용해 컴퓨터를 인증**하는 보안이 강화된 안전한 방법으로 정보를 교환하는 방식이다. 비밀 키는 말 그대로 외부에 공개되지 않는 키이며, 공개 키는 외부로 공개되는 키를 말한다.

**사용자 컴퓨터의 퍼블릭 키를 깃허브 서버에 저장하면, 그 뒤로 원격 저장소에 접근할 때마다 사용자 컴퓨터의 비밀 키와 깃허브 서버의 퍼블릭 키를 비교한다. 두 키가 서로 부합한다면 컴퓨터와 서버가 연결된다.**

### [SSH를 통한 GitHub 연결](https://docs.github.com/ko/authentication/connecting-to-github-with-ssh)

https를 통한 연결은 권장되지 않는 방식임

1. 터미널을 열어 홈 디렉토리로 이동해, SSH키를 생성한다.

```
$ cd
$ ssh-keygen
```

2. .ssh 디렉토리 안에 생성된 공개키와 비밀키를 확인한다.

<pre><code>// id_rsa.pub이 공개키
// id_rsa가 비밀키

<strong>$ cd ~/.ssh
</strong><strong>$ ls -la
</strong></code></pre>

3. 공개키를 복사한다.

```
// ssh-rsa 복사

$ cd ~/.ssh
$ cat id_rsa.pub
```

4. 깃허브에 공개키를 등록한다.

\[깃허브] -> \[사용자 아이콘] -> \[Settings] -> \[SSH and GPG keys] -> \[New SSH Key] 등록
