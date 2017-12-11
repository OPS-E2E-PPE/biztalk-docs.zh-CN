---
title: "如何部署 BAM 定义 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094a37d90db41e505adeaec3a31ece9128785e04
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-bam-definitions"></a>如何部署 BAM 定义
管理员使用**部署所有**BAM 管理实用工具命令以部署来自 Excel 工作簿或 XML 定义文件的 BAM 定义导出从工作簿。 当你执行的完整安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，配置向导将自动配置 BAM 配置 XML。  
  
> [!NOTE]
>  如果有多个用户使用用于 Excel 的 BAM 外接程序，我们建议他们使用同一版本的 Microsoft 数据访问组件 (MDAC)。 否则，可能会出现兼容性问题。 具体而言，如果在一台安装了较新版本的 MDAC 的计算机上创建一个模板，然后试图在安装了较旧版本的 MDAC 的计算机上打开它，则会出现编译器错误。  
  
> [!NOTE]
>  每个数据项（例如，城市）只能用于一个数据维度（例如，位置）。 不能在其他数据维度（例如，地区）中再次使用城市。  
  
> [!IMPORTANT]
>  建议你在部署 BAM Excel 工作簿 (.xls) 之前，先验证其安全性。 你可以在管理计算机上使用 Excel 来验证 BAM Excel 工作簿的安全性。 在部署工作簿之前，将其打开，并确保的宏安全性已设为高，且没有任何警告。  
  
> [!IMPORTANT]
>  在 BAM 数据库中，"BAM_\<...\>"为所有 SQL 实体保留的命名约定 (表、 索引、 存储的过程、 角色等.)。*不这样做*使用此命名约定来创建任何 SQL 实体; 这类用法可能会导致未定义的行为。  
  
 在部署 BAM 定义 XML 文件之前，必须确保用于创建此文件的区域设置与用于部署此文件的计算机的区域设置相匹配。 例如，如果你在运行日文版 Microsoft Windows 的计算机上创建该文件，则用于部署该文件的计算机必须设置为日文区域设置。 如果文件和计算机设置不匹配，则必须将用于运行 BAM 管理实用程序的计算机切换到正确的区域设置，并且必须在运行实用程序前重新启动该计算机。  
  
> [!NOTE]
>  BAM 定义 XML 文件不能包含使用多种语言编写的文本，除非所有语言都使用同一代码页，或者文件中只包括两种语言且其中一种是英语。  
  
 有关更改计算机上的区域设置的信息，请参阅你的操作系统的帮助。  
  
### <a name="to-deploy-a-bam-definition"></a>部署 BAM 定义  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到的跟踪文件夹中，通过键入**C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking**在命令提示符。 按 **Enter**。  
  
3.  类型**bm 部署所有-DefinitionFile:\<BAM 定义文件\>**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)