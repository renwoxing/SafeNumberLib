# SafeNumberLib

使用方法
=======

```
#import <SafeNumberLib/SafeNumberLib.h>
```

### 用户信息接口

* 获取验证码成功
```
[SN_UserInfoManager getCodeWithPhoneNumber:@"13811111111" completion:^(SN_Error *error) {
  if (!error) {
    NSLog(@"获取验证码成功");
  } else {
        
  }
}];
```
* 登录
```
[SN_UserInfoManager loginWithPhoneNumber:@"13811111111" code:@"1234" completion:^(SN_Error *error, SN_UserModel *user) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", user);
    }
}];
```
* 获取Cookie
```
[SN_UserInfoManager getCookieCompletion:^(SN_Error *error) {
    if (error) {
        NSLog(@"%@",error. message);
    }
}];
```
* 登出
```
[SN_UserInfoManager logoutCompletion:^(SN_Error *error) {
    if (!error.success) {
        NSLog(@"logout failure");
    } else {
        NSLog(@"logout success");
    }
    NSLog(@"%@", error.message);
}];
```
* 获取用户信息
```
[SN_UserInfoManager getUserInfoWithPhoneNumber:@"13811111111" completion:^(SN_Error *error, SN_UserModel *user) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"user info %@", user.dictionaryValue);
    }
}];
```
* 更新昵称
```
[SN_UserInfoManager updateUserNicknameWithPhoneNumber:@"13811111111" nickname:@"nickname" completion:^(SN_Error *error) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"更新昵称成功");
    }
}];
```
* 更新性别
```
[SN_UserInfoManager updateUserSexWithPhoneNumber:@"13811111111" sex:@"B" completion:^(SN_Error *error) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"更新性别成功");
    }
}];
```
* 上传用户头像
```
UIImage *image = [UIImage imagedWithName:@""];
[SN_UserInfoManager uploadUserAvatarWihtPhoneNumber:@"13811111111" image:image completion:^(SN_Error *error) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"上传用户头像成功");
    }
}];
```
* 校验原手机号码
```
[SN_UserInfoManager validOldMobileWithPhone:@"13811111111" code:@"1234" completion:^(SN_Error *error) {
    if (error.success) {
        NSLog(@"成功 %@", error.message);
    } else {
        NSLog(@"失败 %@", error.message);
    }
}];
```
* 更换手机号码
```
[SN_UserInfoManager bindNewMobilePhone:@"13811111111" newPhone:@"13811111112"code:@"1234" completion:^(SN_Error *error) {
    if (error.success) {
        NSLog(@"成功 %@", error.message);
    } else {
        NSLog(@"失败 %@", error.message);
    }
}];
```


