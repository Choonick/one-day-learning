
### 1. css 선택자

ul li{
 ul 태그안에 모든 li태그를 선택한다.
}

ul > li{ 
	ul태그안의 바로 아래 자식만 선택한다.
}


<a href="http://www.nextree.co.kr/p8468/">참고 사이트</a>


### 2. not a function
```
  dismiss() {
    this.viewCtrl.dismiss();
  }
```

이렇게 안 띄면 안된다. ```dismiss(){}```


### 3. ionic2 backButtom 숨기기
```
<ion-navbar hideBackButton="true">
    <ion-title>Sub Page</ion-title>
</ion-navbar>
```

### 4. ionic2 component 사용하기
#### .html

```
<test-com [input]="" (output)="">
	
</test-com>
```

#### .ts
```
EventEmitter, ...
@Input() userName;
@Output() test: EventEmitter<any> = new EventEmitter();
....
```


#### 5. git 사용자 변경하기
등록된 사용자 확인

```
git config --list
```

```
git config --global user.name "choonick"
git config --global user.email "wecube.1@gmail.com"
```
