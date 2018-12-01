积分墙开源系统,基于 FeehiCMS 开发,并启用swoole扩展模块
===============================

FeehiCMS 是一个基于Yii2的cms系统,自带了一些常用扩展,非常适用开发者作为基础程序二次开发,以下是FeehiCMS的相关文档

[![Latest Stable Version](https://poser.pugx.org/feehi/cms/v/stable)](https://packagist.org/packages/feehi/cms)
[![License](https://poser.pugx.org/feehi/cms/license)](https://packagist.org/packages/feehi/cms)
[![Build Status](https://www.travis-ci.org/liufee/cms.svg?branch=master)](https://www.travis-ci.org/liufee/cms)


功能列表
-------
用户模块
-------
    用户列表
        用户表: user_id, 用户头像,昵称,广告标识符号idfa,设备唯一标识(uuid),手机号,姓名,来源(自然用户,邀请唯一值),是否有卡,状态,机型,系统,是否越狱,创建时间,最后访问时间
        详情表: user_id, 账户余额,总收入,总支出, 任务次数/收入,邀请次数/收入,签到次数/收入,分成次数/收入,兑换次数/支出,  
    用户编辑
    用户禁用
        用户状态:禁用,可用

手机号管理
    表: phone_id, 用户id, 创建时间,更新时间
设备认证
    ios设备uuid认证
    设备列表(uuid维度)
        设备表: device_id, 机型,系统,idfa,uuid,用户id,创建时间,更新时间

收支模块
    收支列表
        类型: 任务,邀请,签到,分成,兑换
        表:bill_id,订单id,用户id,金额(只存正数),类型类型,业务id,创建时间,更新时间

用户任务记录    

消息模块
    用户消息(推送)记录

兑换(提现)模块
    兑换列表
        表: exchange_id,hash, 用户id,兑换金币,折算金额,类型(微信提现),支付服务方订单id,是否加急处理(特殊场景适用,如 增加手续费),兑换状态(审核状态)
    审核通过
    审核拒绝

签到模块
    用户签到记录

微信模块
    微信公众号配置
    微信用户表
    微信支付记录表(定时任务拉取)

验证码模块
    短信验证码记录
    发送验证码

推广(邀请,渠道)模块
    推广记录
        表:invite_id, 受邀用户id, 来源标识hash, 创建时间,更新时间
    推广信息表(每个用户或者渠道的配置表)
        表:invite_hash_id, hash 值, 类型(用户,渠道),关联id(用户id,渠道id),创建时间,更新时间
    

app配置模块
    公告
    兑换选项(金额列表, 是否审核)

广告模块 
    创建应用(通过苹果接口拉取app数据)
    创建广告(订单)
    复制订单(续单操作)
    状态:启动,停止(启动的可激活,停止的不可激活)
    展示:未设置,显示.隐藏(此设置优先状态设置,默认未设置,根据广告状态控制是否展示,可增加黑白名单设置)
    关键词:可选,可新增,投放量只针对当前订单有效,启动的不可以修改

统计报表
    用户报表
        日活(当日活跃用户),日新增(当日注册用户),1-15日留存(保留最大值,每日根据前一天的用户留存记录查询是否增加留存总天数)
    广告报表
        月/天/小时
            广告投放数,广告激活数,广告领取数(点击:(排重/非排重)),广告展示数量(排重/非排重)
        实时
            广告id,用户id,用户idfa,操作类型,操作时间
