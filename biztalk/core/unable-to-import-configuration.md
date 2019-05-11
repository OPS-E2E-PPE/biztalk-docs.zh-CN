---
title: 无法导入配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dd4c5b2264c5f9ace89b206f2e948083a606b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292743"
---
# <a name="unable-to-import-configuration"></a>无法导入配置
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                   无法从文件导入配置"{0}"                   |
  
## <a name="explanation"></a>解释  
 可能有多个导致此错误的原因：  
  
-   配置文件可能包含给定编码中的无效字符。  
  
-   可能缺少根元素。  
  
-   根级别的数据可能无效。  
  
> [!NOTE]
>  这种情况下，用户执行任何操作，仅适用于 Wcf-custom 和 Wcf-customisolate 适配器。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程导入有效的配置文件。  
  
#### <a name="to-import-a-valid-configuration-file"></a>若要导入有效的配置文件  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**导入/导出**选项卡。  
  
9. 单击“导入” 。 导入有效且完整的配置文件。  
  
   你还可以通过使用服务配置编辑器中打开它来验证配置文件的有效性 **(开始 > 所有程序 > Windows SDK)** （此步骤假设已安装 Windows SDK。）打开**svcConfigEditor.exe**并验证配置文件的每个属性。