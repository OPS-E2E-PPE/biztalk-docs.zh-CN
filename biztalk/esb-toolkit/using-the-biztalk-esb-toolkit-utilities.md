---
title: 使用 BizTalk ESB 工具包实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fcea7d2d7818b59ffae75754d04f5102e5f91c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396420"
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a>使用 BizTalk ESB 工具包实用工具
本部分介绍各种实用程序作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 **ESB 路线导入实用程序**  
  
 此实用工具位于的 \bin 目录下[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 EsbImportUtil.exe。 此实用工具可以用于发布或部署到 ESBItineraryDB 数据库路线 XML。  
  
 该实用工具的语法如下所示：  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 它可以接受的各种参数如下所示：  
  
 /?:\<显示参数帮助\>  
  
 /f:\<路线的 xml 文件路径\>  
  
 /c: \<published &#124; deployed\>  
  
 /n:\<默认的旅行计划名称\>  
  
 /v:\<默认路线版本 （格式 major.minor）\>  
  
 /o:\<无提示覆盖\>  
  
 以下是有关如何使用此实用工具的示例。  
  
 若要将发布到行程数据库：  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 若要将部署到行程数据库：  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 **SSO 配置保留实用程序**  
  
 此实用工具位于的 \bin 目录下[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 Microsoft.Practices.ESB.PersistConfigurationTool.exe。 此实用工具可以用于持久保存到 BizTalk SSO 数据库的 ESB 配置信息。 这也用于查看配置信息和从 SSO 数据库中删除的配置信息。  
  
 该实用工具的语法如下所示：  
  
 **若要添加一个配置节：**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  如果未提供 /S，则将添加以下各节： connectionStrings，esb、 esb.resolver 和 cachingConfiguration。  
  
 **若要删除的节：**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 若要查看现有节，请使用 /V 开关使用应用程序和部分开关。  
  
 若要设置管理员组名称，请使用 AG:AdminGroupName 开关。  
  
 若要设置的用户组名称，使用 UG:UserGroupName 开关。