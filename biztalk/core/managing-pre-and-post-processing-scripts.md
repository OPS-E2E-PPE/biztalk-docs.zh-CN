---
title: 管理前期和后期处理脚本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262469"
---
# <a name="manage-pre--and-post-processing-scripts"></a>管理前期和后期处理脚本

## <a name="overview"></a>概述
本部分介绍如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理预处理脚本和后处理脚本。 您可以创建要在导入、安装或卸载（删除）BizTalk 应用程序时运行的脚本，并随后将其添加到应用程序中。 添加脚本时，您要指定它是预处理脚本（在导入、安装前和卸载后运行）还是后处理脚本（在导入或安装后及卸载前运行）。  
  
 如果在导出应用程序时选择该脚本，则该脚本将被包含在应用程序的 .msi 文件中。 安装、卸载或导入应用程序时，该脚本将自动运行，具体运行情况取决于您所编写的脚本内容。 有关创建和使用脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [将预或后续处理脚本添加到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [更改预或后续处理脚本的目标位置](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [从应用程序中删除预或后续处理脚本](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)