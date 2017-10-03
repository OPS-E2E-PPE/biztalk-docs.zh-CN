---
title: "无法导入配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e565b466e4f9ce8af3745948952b4318a029ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-import-configuration"></a>无法导入配置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法从文件“{0}”导入配置|  
  
## <a name="explanation"></a>解释  
 此错误可能由多个原因所致：  
  
-   配置文件可能在给定编码中包含无效字符。  
  
-   根元素可能丢失。  
  
-   根级别的数据可能无效。  
  
> [!NOTE]
>  在这种情况下，用户操作仅适用于 WCF-Custom 和 WCF-CustomIsolate 适配器。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程导入有效的配置文件。  
  
#### <a name="to-import-a-valid-configuration-file"></a>导入有效的配置文件  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**导入/导出**选项卡。  
  
9. 单击“导入” 。 导入有效且完整的配置文件。  
  
 你还可以通过使用服务配置编辑器中打开它来验证配置文件的有效性**(启动 > 所有程序 > Windows SDK)** （此步骤假定你安装的 Windows SDK。）打开**svcConfigEditor.exe**并验证配置文件的每个属性。