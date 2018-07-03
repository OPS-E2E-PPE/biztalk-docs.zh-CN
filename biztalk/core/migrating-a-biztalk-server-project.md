---
title: 迁移 BizTalk Server 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a4dde72-6555-4bf6-b90e-676aa65312ff
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b0aa77fc9b30d3f365cf48f084b7d46bdbbb1b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989238"
---
# <a name="migrating-a-biztalk-server-project"></a>迁移 BizTalk Server 项目
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 有关开发的项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用迁移到较新的环境[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]转换。 有关支持的迁移版本的列表，请参阅[支持的升级路径和安装指南](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx)。  

## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a>在运行转换向导之后更改 BizTalk 项目  
 下表显示如何[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]项目配置名称的更改，而其中一些特定的配置属性会重新定位项目之后转换到更新版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。 大部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关的项目设置位于**部署**项目设计器选项卡。  


| [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目 | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|             **嵌入跟踪信息**输出配置属性             |      **定义 TRACE 常数**上生成选项**生成**项目设计器选项卡       |
|           **生成调试信息**输出配置属性           |      **定义 DEBUG 常数**上生成选项**生成**项目设计器选项卡       |
|              **符合 BPEL 规范**代码生成配置属性              |       **符合 BPEL 规范**代码项目属性窗口中的生成属性        |

> [!NOTE]
>  现在 BizTalk 项目有两种生成类型：**发行**并**调试**，它取代了**开发**并**部署**的前面版本。 但是，您仍然可以看到**开发**并**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。  
> 
> [!CAUTION]
>  仅 *.btproj 和\*。 由于选择的备份选项在转换期间备份 btproj.user 项目文件。 其他文件必须手动备份。  
> 
> [!CAUTION]
>  对自动生成的项目（例如 XSD 和 ODX 文件）的任何自定义都将在转换过程中丢失。 这适用于 web 引用添加到 BizTalk 项目时生成的 XSD 文件。  

## <a name="project-migration-and-delay-signing"></a>项目迁移和延迟签名  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目使用[延迟签名](http://go.microsoft.com/fwlink/p/?LinkId=140992)可能会在转换为在生成过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果发生这种情况**生成序列化程序集**已迁移的项目配置未设置为生成设置**关闭**。  

## <a name="project-migration-and-msmqt"></a>项目迁移和 MSMQT  
 MSMQT 不再是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分。 这会如何影响项目迁移的详细信息，请参阅主题[MSMQT 弃用](../core/msmqt-deprecation.md)。  

## <a name="project-conversion-requires-the-project-and-solution-file"></a>项目转换需要项目和解决方案文件  
 如果您尝试转换 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目但没有解决方案文件，则您将收到以下错误：  

 **转换项目文件时出错。子元素\<BIZTALK\>元素的\<VisualStudioProject\>无效。**  

 项目转换需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中的解决方案文件 (.sln)。 如果该解决方案文件不可用，则您必须使用 [!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] 创建一个解决方案文件，并将 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 项目添加到该解决方案。 然后运行 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 转换向导。  

> [!NOTE]
>  您可以将项目与 Visual Studio 中使用仅在项目文件 (.btproj) 转换。