---
title: 管理架构 |Microsoft Docs
description: 使用 BizTalk 管理可以使用在 BizTalk Server 中，包括显示和隐藏属性架构，查看其 XSD，启用跟踪
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5632e79-b182-41c9-9138-eb88b44e3172
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c39d6bd414a1f9558e058881c41f6dd9bd1e5d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531139"
---
# <a name="manage-schemas"></a>管理架构

## <a name="overiew"></a>概述
本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来管理架构。 管道和业务流程使用架构来表示将处理的消息。  
  
 在创建架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。 不能单独; 将架构添加到应用程序架构添加到应用程序，如下所示：  
  
- 当添加包含到应用程序，架构的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含 BizTalk 程序集包含架构，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序包含来自的架构的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
  有关架构的背景信息，请参阅[架构](../core/schemas.md)。 有关开发架构的信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [显示和隐藏属性架构](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [查看某一架构的架构定义 (XSD)](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [为架构配置跟踪](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [从应用程序中删除架构](../core/how-to-remove-a-schema-from-an-application.md)