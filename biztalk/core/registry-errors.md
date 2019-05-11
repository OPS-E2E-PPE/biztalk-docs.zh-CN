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
ms.openlocfilehash: afca0825ee04334385925d08e3edb0d0ed055c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398002"
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
 确保对注册表有读取访问权限。 若要访问注册表，请确保你具有管理员权限或计算机的管理员联系。
 
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
 此错误表示无法访问注册表，并且该密钥具有不正确的值。  
  
## <a name="user-action"></a>用户操作  
 确保对注册表有读取访问权限。 确保密钥具有正确的值。 若要访问注册表，请确保你具有管理员权限或计算机的管理员联系。 