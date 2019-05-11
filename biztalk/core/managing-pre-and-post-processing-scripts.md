---
title: 管理预处理和后处理脚本 |Microsoft Docs
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
ms.openlocfilehash: b39deb7d053ec21677e519852184550d6f3c793d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328048"
---
# <a name="manage-pre--and-post-processing-scripts"></a>管理预处理和后处理脚本

## <a name="overview"></a>概述
本部分说明了使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理预处理脚本和后处理脚本。 您可以创建你想要导入、 安装或卸载 BizTalk 应用程序时运行的脚本 （删除），并将脚本添加到应用程序。 当您添加脚本时，指定是否在运行之前导入、 安装和卸载之后，预处理脚本或后处理脚本，运行导入或安装之后并在卸载之前。  
  
 如果导出应用程序时选择的脚本，该脚本将包含在应用程序的.msi 文件。 当你安装、 卸载或导入应用程序时，该脚本自动运行，具体取决于如何所编写的脚本。 有关创建和使用脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [向应用程序添加预处理脚本和后期处理脚本](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [更改预处理脚本或后期处理脚本的目标位置](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [从应用程序中删除预处理脚本或后期处理脚本](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)