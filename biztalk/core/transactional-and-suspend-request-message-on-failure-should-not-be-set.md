---
title: 事务选项&quot;事务性&quot;和错误处理选项&quot;在失败时挂起请求消息&quot;应不能同时设置为 false |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3818ddba18b89aedd1185f5ad87f3682dd5686a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971414"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a>事务选项&quot;事务性&quot;和错误处理选项&quot;在失败时挂起请求消息&quot;应不能同时设置为 false
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| 产品版本 |                                                                            [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                            |
|    事件 ID     |                                                                                                        0                                                                                                         |
|  事件源   |                                                                                                        0                                                                                                         |
|    组件    |                                                                                                        0                                                                                                         |
|  符号名称  |                                                                                                        0                                                                                                         |
|  消息正文   | 因为消息可能会丢失，所以，事务选项“事务性”和错误处理选项“失败时挂起请求消息”不应该设置为 False。 请将其中一个或两个选项设置为 True。 |
  
## <a name="explanation"></a>解释  
 在 Wcf-netmsmq 适配器中，选项**事务性**并**在失败时挂起请求消息**应不能同时设置为 false （未选中）。 当消息没有被挂起并且没有存储在 MessageBox 中时，如果提交失败的消息没有作为事务回滚，则消息可能会丢失。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程验证适配器设置。  
  
#### <a name="to-verify-adapter-settings"></a>验证适配器设置的步骤  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**Wcf-netmsmq 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 在中**事务**部分中，确定是否**事务性**检查。  
  
10. 单击**消息**选项卡。  
  
11. 确定是否**失败时挂起请求消息**检查。  
  
    > [!NOTE]
    >  这些步骤只适用于接收位置。