---
title: 迁移 BizTalk Server 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a4dde72-6555-4bf6-b90e-676aa65312ff
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2752203b0498a6cd5a4a8b6df6bc558c444e355
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="migrating-a-biztalk-server-project"></a>迁移 BizTalk Server 项目
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 为开发项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可迁移到较新的环境中，通过使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换。 有关支持的迁移版本的列表，请参阅 [支持升级路径和安装指南](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx)。  
  
## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a>BizTalk 项目更改后运行转换向导  
 下表显示如何[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]项目配置名称更改，而其中一些特定的配置属性重新项目后定位到较新转换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。 大部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关的项目设置位于**部署**项目设计器选项卡。  
  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目|  
|------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|  
|**跟踪信息嵌入** 输出配置属性|**定义 TRACE 常数** 生成选项 **生成** 项目设计器选项卡|  
|**生成调试信息** 输出配置属性|**定义 DEBUG 常数** 生成选项 **生成** 项目设计器选项卡|  
|**BPEL 法规遵从性** 代码生成配置属性|**BPEL 法规遵从性** 代码项目属性窗口中的生成属性|  
  
> [!NOTE]
>  BizTalk 项目现在有两个生成类型︰ **版本** 和 **调试**, ，哪些替换 **开发** 和 **部署** 的早期版本。 但是，你仍然可以看到**开发**和**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。  
  
> [!CAUTION]
>  仅 *.btproj 和 \*。 由于选择转换过程中的选项备份备份 btproj.user 项目文件。 其他文件必须手动备份。  
  
> [!CAUTION]
>  对自动生成的项目（例如 XSD 和 ODX 文件）的任何自定义都将在转换过程中丢失。 这适用于生成的 web 引用添加到 BizTalk 项目时的 XSD 文件。  
  
## <a name="project-migration-and-delay-signing"></a>项目迁移和延迟签名  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目使用[延迟签名](http://go.microsoft.com/fwlink/p/?LinkId=140992)后可能失败并在生成过程中要转换为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 可能的原因是 **生成序列化程序集** 已迁移的项目配置未设置为生成设置 **关闭**。  
  
## <a name="project-migration-and-msmqt"></a>项目迁移和 MSMQT  
 MSMQT 不再是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分。 有关如何这可能会影响项目迁移的详细信息，请参阅主题[MSMQT 弃用](../core/msmqt-deprecation.md)。  
  
## <a name="project-conversion-requires-the-project-and-solution-file"></a>项目转换需要项目和解决方案文件  
 如果您尝试转换 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目但没有解决方案文件，则您将收到以下错误：  
  
 **转换项目文件时出错。子元素\<BIZTALK\>元素的\<VisualStudioProject\>无效。**  
  
 项目转换需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中的解决方案文件 (.sln)。 如果该解决方案文件不可用，则您必须使用 [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] 创建一个解决方案文件，并将 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目添加到该解决方案。 然后运行 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 转换向导。  
  
> [!NOTE]
>  你可能能够将转换的项目文件 (.btproj) 仅使用 Visual Studio 项目。