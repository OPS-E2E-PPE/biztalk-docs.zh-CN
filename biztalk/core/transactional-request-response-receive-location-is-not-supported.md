---
title: 事务性请求响应接收位置不支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37cea795e097596862e14f64b825696511ffbe6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399202"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a>不支持事务性请求响应接收位置
## <a name="details"></a>详细信息  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |         事务性请求响应接收位置不受支持。          |

## <a name="explanation"></a>解释  
 此错误表示已将事务设置为 WCF 请求-响应接收位置启用。 为请求-响应接收位置的 messagebox 数据库由于 BizTalk 中不支持事务。  

## <a name="user-action"></a>用户操作  
 对于标准 WCF 适配器，请转到代码配置请求-响应接收位置。 絋粄**EnableTransaction**中的 XML 数据元素**TransportTypeData**属性**ITransportInfo**界面被设置为**False**.  

 对于 Wcf-custom 适配器：  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  

9. 确保 transactionFlow 属性设置为**False**。
