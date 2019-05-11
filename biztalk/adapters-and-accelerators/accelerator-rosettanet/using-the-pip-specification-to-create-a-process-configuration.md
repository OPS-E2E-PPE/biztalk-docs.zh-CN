---
title: 使用 PIP 规范创建流程配置 |Microsoft Docs
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21933797f37b32a4131c57181829f2380bafe061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299915"
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a>使用 PIP 规范创建流程配置
从 RosettaNet 组织 （从 rosettanet.org 下载得到） 下载合作伙伴接口流程 (PIP) 后，下载包包括 PIP 规范文档。 本文档包含有关要创建在流程配置时使用哪些设置[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a>如何 PIP 设置映射到 PIP 规范  
 下表描述了如何将 PIP 设置映射到 RosettaNet PIP 规范中的信息。  
  
|流程配置设置|PIP 规范中的信息|  
|-----------------------------------|------------------------------------------|  
|流程代码|在标题页上，例如，"PIP3A4"副标题|  
|版本|在标题页上，例如，"02.02.00"PIP 版本标识符副标题|  
|进程名称|在标题页上，例如，"请求采购订单"副标题|  
|说明 （常规选项卡）|第 3.1 节业务过程定义|  
|要求不可否认性|表 3-3:业务活动性能控件|  
|若要确认 （秒） 的时间|表 3-3:业务活动性能控件|  
|是否要求授权|表 3-3:业务活动性能控件|  
|要求永久保密|（从 PIP 规范没有引用）|  
|是否要求安全传输？|表 4-3:消息交换控制|  
|为单一操作|部分 4.3，业务事务对话框规范|  
|不可否认性和内容的|表 3-3:业务活动性能控件|  
|重试次数|表 3-3:业务活动性能控件|  
|若要执行的时间|表 3-3:业务活动性能控件|  
|“属性”|表 3-3:业务活动性能控件 （活动名称）|  
|类型|（从 PIP 规范-供将来使用不引用）|  
|说明 （发起方和响应选项卡）|表 3-4:PIP 的业务文档|  
|名称 （发起方和响应选项卡）|表 3-4:PIP 的业务文档|  
|角色 （发起方和响应选项卡）|表 3-1:合作伙伴角色描述|  
|角色说明 （发起方和响应选项卡）|表 3-1:合作伙伴角色描述|  
|角色类型 （发起方和响应选项卡）|表 3-1:合作伙伴角色描述|  
|服务|表 4-1:网络组件规范|  
|服务分类|表 4-1:网络组件规范|  
  
## <a name="see-also"></a>请参阅  
 [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)