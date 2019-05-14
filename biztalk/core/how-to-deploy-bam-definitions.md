---
title: 如何部署 BAM 定义 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58d2711ee5bdf9e280ad32610031d5720d8d2c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385276"
---
# <a name="how-to-deploy-bam-definitions"></a>如何部署 BAM 定义
管理员使用**部署所有**从工作簿导出 BAM 管理实用程序命令以部署 BAM 定义从 Excel 工作簿或 XML 定义文件。 当你执行的完整安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，配置向导将自动配置 BAM 配置 XML。  
  
> [!NOTE]
>  如果多个用户正在用于 Excel 的 BAM 外接程序，我们建议，它们具有相同版本的 Microsoft 数据访问组件 (MDAC)。 否则，可能会出现兼容性问题。 具体而言，如果使用较新版本的 MDAC 的计算机上创建一个模板，然后尝试使用旧版本的 MDAC 的计算机上打开它，将发生编译器错误。  
  
> [!NOTE]
>  可以使用每个数据维度 （例如，位置） 的仅一个数据项 （例如，城市）。 不能在另一个数据维度，例如，地区中再次使用城市。  
  
> [!IMPORTANT]
>  我们建议在部署它们之前验证 BAM Excel 工作簿 (.xls) 的安全性。 在管理计算机上使用 Excel 来验证 BAM Excel 工作簿的安全性。 在部署某一工作簿之前，将其打开，并确保宏安全性设置为高，不会出现任何警告。  
  
> [!IMPORTANT]
>  在 BAM 数据库中，"BAM_\<...\>"命名约定保留的所有 SQL 实体 (表、 索引、 存储的过程、 角色等。...)。*不这样做*使用此命名约定创建任何 SQL 实体; 此类使用可能会导致未定义的行为。  
  
 部署 BAM 定义 XML 文件之前，必须确保用于创建此文件的区域设置与要在其部署它的计算机的区域设置相匹配。 例如，如果您创建运行 Microsoft Windows 的日语版本的计算机上的文件，在部署该文件的计算机必须设置为日文区域设置。 如果该文件和计算机设置不匹配，必须切换用于运行 BAM 管理实用程序到正确的区域设置的计算机和您必须重新启动它之前运行此实用程序。  
  
> [!NOTE]
>  BAM 定义 XML 文件不能包含多个语言的文本，除非所有语言都使用同一代码页，或只有两种语言都包括在内并且其中一种是英语。  
  
 有关更改您的计算机上的区域设置的信息，请参阅您的操作系统的帮助。  
  
### <a name="to-deploy-a-bam-definition"></a>若要部署的 BAM 定义  
  
1.  打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过键入导航到跟踪文件夹**C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking**在命令提示符处。 按 **Enter**。  
  
3.  类型**bm 部署全部-DefinitionFile:\<BAM 定义文件\>**。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)