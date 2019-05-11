---
title: 无法导出客户端终结点配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce781105c96f12705605e7c97f0e5229d2017f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292797"
---
# <a name="unable-to-export-client-endpoint-configuration"></a>无法导出客户端终结点配置
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |              无法导出客户端终结点配置为"{0}"               |
  
## <a name="explanation"></a>解释  
 此错误指示以下值之一：  
  
-   用户可能没有向目标写入的权限。  
  
     \- 或 -  
  
-   某些所需的属性未正确指定，如**地址 (URI)** 并**绑定类型**。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程来验证用户权限并确认**地址 (URI)** 并**绑定类型**设置是否有效。  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a>若要验证用户权限并确认设置  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到应用程序，并找到你传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 请确保允许写入到目标文件夹。  
  
10. 检查**行为**选项卡和**终结点标识**中的设置**常规**选项卡，以确保它们有效。  
  
> [!NOTE]
>  必须为的目标文件夹具有写入权限。 与计算机的管理员联系以获取这些权限。