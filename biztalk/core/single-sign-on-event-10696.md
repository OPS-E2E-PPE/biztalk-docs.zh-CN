---
title: 单一登录： 事件 10696 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3332a8104b96731a1fcf75267ec6fd69100c441a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968566"
---
# <a name="single-sign-on-event-10696"></a>单一登录： 事件 10696
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10696                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    N\A                                    |
|  符号名称  |                SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION                |
|  消息正文   | 检测到进度文件已损坏。%r<br /><br /> 文件名称： %1 |

## <a name="explanation"></a>解释  
 此错误事件表明 SSO 已与 SSO 数据库重新建立联系，但是由于进度文件损坏而无法对其进行读取。 如果 SSO 无法打开进度文件，则将在第一个重播文件的开始记录处启动。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
