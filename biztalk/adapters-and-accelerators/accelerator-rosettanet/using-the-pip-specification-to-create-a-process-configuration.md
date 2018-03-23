---
title: 使用 PIP 规范创建过程配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f32e5a9e035f6009f5450eb48ae8286159f05
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a>使用 PIP 规范创建过程配置
从 RosettaNet 组织 （从 RosettaNet.org) 下载伙伴接口过程 (PIP) 后，下载包包括 PIP 规范文档。 本文档包含要在创建中的过程配置时使用哪些设置的指导[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a>如何 PIP 设置映射到 PIP 规范  
 下表介绍 PIP 设置如何映射到 RosettaNet PIP 规范中的信息。  
  
|过程配置设置|PIP 规范中的信息|  
|-----------------------------------|------------------------------------------|  
|进程代码|在标题页上，例如，"PIP3A4"副标题|  
|版本|在标题页上，例如，"02.02.00"PIP 版本标识符副标题|  
|进程名称|在标题页上，例如，"请求采购订单"副标题|  
|说明 （常规选项卡）|第 3.1 节业务过程定义|  
|不可否认性所需|表 3-3： 业务活动性能控件|  
|时间以确认 （秒）|表 3-3： 业务活动性能控件|  
|是否要求授权？|表 3-3： 业务活动性能控件|  
|要求永久保密|（PIP 规范中未引用）|  
|是所需的安全传输？|表 4-3： 消息 Exchange 控件|  
|是单个操作|部分 4.3，业务事务对话框规范|  
|不可否认性的源和内容|表 3-3： 业务活动性能控件|  
|重试计数|表 3-3： 业务活动性能控件|  
|执行时间|表 3-3： 业务活动性能控件|  
|名称|表 3-3： 业务活动性能控件 （活动名称）|  
|类型|（从 PIP 规格-供以后使用未引用）|  
|说明 （发起方和响应选项卡）|表 3-4: PIP 商业文档|  
|名称 （发起方和响应选项卡）|表 3-4: PIP 商业文档|  
|角色 （发起方和响应选项卡）|表 3-1： 伙伴角色描述|  
|角色描述 （发起方和响应选项卡）|表 3-1： 伙伴角色描述|  
|角色类型 （发起方和响应选项卡）|表 3-1： 伙伴角色描述|  
|服务|表 4-1： 网络组件规范|  
|服务分类|表 4-1： 网络组件规范|  
  
## <a name="see-also"></a>另请参阅  
 [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)