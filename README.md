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

### 安全号码

* 查询安全号码
```
[SN_Query querySafeNumberWithQuery:@"搜索字符串" phoneLength:@"11" phoneType:@"" phonePrice:@"" completion:^(SN_Error *error, NSArray<SN_NumberAndPriceModel *> *results) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", results);
    }
}];
```
* 获取号码价格、号码类型、号码长度
```
[SN_Query getNumberPtlCompletion:^(SN_Error *error, SN_NumPtlModel *numberFilteModel) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", numberFilteModel);
    }
}];
```
* 我的安全好列表
```
[SN_Query mySafeNumberListWithPhone:@"13811111111" completion:^(SN_Error *error, NSArray<SN_SafeNumberModel *> *results) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", results);
    }
}];
```
* 更改安全号码备注
```
[SN_Query changeRemarkWithPhone:@"13811111111" remarks:@"备注" sid:@"123142" completion:^(SN_Error *error) {
    if (error.success) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", error.message);
    }
}];
```
* 是否停用安全号码
```
[SN_Query changeIsDisableWithPhone:@"13811111111" sid:@"123142" phoneState:SN_PhoneStateDisable completion:^(SN_Error *error) {
    if (error.success) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", error.message);
    }
}];
```
* 购买号码页面获取的默认号码及套餐
```
[SN_Query queryDefaultSafeNumberPurchaseInfoCompletion:^(SN_Error *error, SN_PackageInfoModel *model) {
    if (!error) {
        NSLog(@"%@", model);
    } else {
        NSLog(@"%@", error.message);
    }
}];
```
* 查询套餐
```
[SN_Query queryPackageWithSid:@"123142" completion:^(SN_Error *error, NSArray<SN_PackageModel *> *list) {
    if (!error) {
        NSLog(@"%@", list);
    } else {
        NSLog(@"%@", error.message);
    }
}];
```
* 安全号详情
```
[SN_Query getSafeNumberDetailWithPhone:@"13811111111" sid:@"123142" completion:^(SN_Error *error, SN_SafeNumberModel *safeNumberModel) {
    if (!error) {
        NSLog(@"%@", safeNumberModel);
    } else {
        NSLog(@"%@", error.message);
    }
}];
```
* 查询安全号
```
[SN_Query querySafeNumberWithPhone:@"13811111111" sid:@"123142" completion:^(SN_Error *error, NSArray<SN_NumberAndPriceModel *> *list) {
    if (error) {
        NSLog(@"%@", error.message);
    } else {
        NSLog(@"%@", list);
    }
}];
```
* 更换安全号码
```
[SN_Query changeSafeNumberWithPhone:@"13811111111" sid:@"123142" newSid:@"123143" completion:^(SN_Error *error) {
    if (error.success) {
        
    } else {
        
    }
    NSLog(@"%@", error.message);
}];
```

### 支付

* 支付
```
SNPaymentType payType = SNPaymentTypeAli;
NSString *sid = @"1234567890";

SN_PayInfoModel *payInfoModel = [[SN_PayInfoModel alloc] init];
payInfoModel.totalfee = @"0.01";//套餐价格
payInfoModel.subject = @"安全号码购买";
payInfoModel.body = [NSString stringWithFormat:@"购买安全号码:%@",sid];
payInfoModel.phone = @"13811111111";
payInfoModel.accountnumber = sid;
payInfoModel.monthdesc = @"三个月";//套餐描述
payInfoModel.month = @"";//套餐有效日期
payInfoModel.ordertype = SNOrderTypePurchase;//支付订单类型(购买和充值)
payInfoModel.paymentway = payType;//支付方式(支付宝和微信)
payInfoModel.orderprice = [NSString stringWithFormat:@"%.0f",0.01];//套餐价格

//应用注册scheme,在Info-Info.plist定义URL types
payInfoModel.appScheme = @"SafeNumberAPI";//支付宝的URL Scheme

[[SN_Payment sharedPayment] startPayWithPayInfo:payInfoModel completion:^(SN_Error *error, SN_OrderResultModel *orderResultModel) {
    if (error) {
        NSLog(@"%@",error.message);
    } else {
        NSLog(@"order is %@", orderResultModel);
    }
}];
```