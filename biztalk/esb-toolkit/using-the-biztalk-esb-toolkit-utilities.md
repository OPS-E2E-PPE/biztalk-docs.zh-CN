---
title: "使用 BizTalk ESB 工具包实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4a8ef2def05e0b77d272463d7a79f937623b1a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a>使用 BizTalk ESB 工具包实用程序
本部分介绍各种实用程序作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 **ESB 路线导入实用程序**  
  
 此实用程序位于 \bin 目录的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 EsbImportUtil.exe。 此实用工具可以用于发布或部署到 ESBItineraryDB 数据库路线 XML。  
  
 实用程序的语法如下所示：  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 它可以接受的各种参数如下所示：  
  
 /？:\<显示帮助的参数\>  
  
 /f:\<路线 xml 文件路径\>  
  
 无\<发布 &#124; 部署\>  
  
 /n:\<默认路线名称\>  
  
 /v:\<默认路线版本 （格式 major.minor）\>  
  
 /o:\<静默覆盖\>  
  
 以下是如何使用此实用工具的示例。  
  
 将发布到路线数据库：  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 若要部署到路线数据库：  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 **SSO 配置保留实用程序**  
  
 此实用程序位于 \bin 目录的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 Microsoft.Practices.ESB.PersistConfigurationTool.exe。 此实用工具可以用于持久保存到 BizTalk SSO 数据库的 ESB 配置信息。 这还可查看配置信息和从 SSO 数据库中删除的配置信息。  
  
 实用程序的语法如下所示：  
  
 **若要添加一个配置节：**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  如果未提供 /S，将添加以下各节： connectionStrings，esb、 esb.resolver 和 cachingConfiguration。  
  
 **若要删除节：**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 若要查看现有的内容，请将应用程序和部分开关用于 /V 开关。  
  
 若要设置管理员组名称，请使用 AG:AdminGroupName 交换机。  
  
 若要设置的用户组名称，使用 UG:UserGroupName 开关。