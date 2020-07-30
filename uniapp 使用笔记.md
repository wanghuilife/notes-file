# 1、获取信息

## 1.1 获取地理位置

```javascript
uni.getLocation({
    type: 'wgs84',
    success: function (res) {
        console.log('当前位置的经度：' + res.longitude,res);
        console.log('当前位置的纬度：' + res.latitude);
	}
});
```

## 1.2 获取用户信息1

```html
<button open-type="getUserInfo" @getuserinfo="wxGetUserInfo">
    <image class="img" src="/static/images/red-m.jpg" alt="">
</button>
```

```javascript
wxGetUserInfo() {
    let _this = this;
    uni.getUserInfo({
        provider: 'weixin',
        success: function(infoRes) {
        	console.log(infoRes, '用户信息')
        },
        fail(res) {}
    });
}
```

## 1.3 获取用户OpenId

```javascript
let that = this;
uni.login({
    provider: 'weixin',
    success: function(loginRes) {
        const { code } = loginRes
        const appid = 'wx9254cb2f9f8e4cc8'; // 小程序appid
        const secret = '5ec832f78c7782b4c303494b7276b543'; //小程序secret
        const url = `https://api.weixin.qq.com/sns/jscode2session?appid=${appid}&secret=${secret}&js_code=${code}&grant_type=authorization_code`
        // 获取openID
        uni.request({
            url: url, // 请求路径
            method: 'GET', //请求方式
            success: result => {
                console.info(result);
            },
            fail: err => {} //失败
        });
    }
});
```

## 1.4 在线客服



```html
<button open-type="contact">联系客服</button>

https://mpkf.weixin.qq.com/cgi-bin/kfloginpage // 网页版登录客服
```

小程序管理-客服-添加客服账号

