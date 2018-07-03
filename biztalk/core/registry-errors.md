---
title: 注册表错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975110"
---
# <a name="registry-errors"></a>注册表错误
诊断和解决 WCF 注册表错误的信息。  

## <a name="failed-to-access-the-registry"></a>未能访问注册表
  
|                 |                                   错误详细信息                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                             无法打开 HKLM\\{0}。                              |
  
### <a name="explanation"></a>解释  
 此错误表明访问注册表失败。  
  
### <a name="user-action"></a>用户操作  
 确保您具有注册表的读取访问权限。 要访问注册表，请确保您具有管理员权限，或者与计算机管理员联系。
 
## <a name="failed-to-obtain-biztalk-install-path"></a>未能获取 BizTalk 安装路径
  
|                 |                                   错误详细信息                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |             未能从 HKLM 获取 BizTalk 安装路径\\{0}\\{1}              |
  
## <a name="explanation"></a>解释  
 此错误表明访问注册表失败，并且该密钥具有不正确的值。  
  
## <a name="user-action"></a>用户操作  
 确保您具有注册表的读取访问权限。 确保密钥具有正确的值。 要访问注册表，请确保您具有管理员权限，或者与计算机管理员联系。 