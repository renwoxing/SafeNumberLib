# SafeNumberLib

使用方法
=======

```
#import <SafeNumberLib/SafeNumberLib.h>
```

### 用户信息接口使用说明

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
