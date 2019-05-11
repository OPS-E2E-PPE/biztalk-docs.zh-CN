---
title: 配置 XML 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a41fdd9689f822736607ecbc7ec1ea0f0fd4f36c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355062"
---
# <a name="configuring-the-xml-file"></a>配置 XML 文件
在安装企业单一登录 (SSO) 时，在扩展目录中安装一个名为 ENTSSO.xml 的 XML 文件。 通过编辑的文件，可定义 ENTSSO 管理代理 (MA) 的所有实例的配置。  
  
 该文件是类似于下面：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a>XML 元素和属性  
 以下列表介绍的元素和 XML 文件中定义的属性。 请注意，此文件中的所有元素和属性名称区分大小写。  
  
 **元素：ENTSSO** -定义单个 ENTSSO MA 实例的配置。 允许多个 ENTSSO 元素。  
  
 **属性： 名称**-定义 ENTSSO 管理代理的实例名称，并且必须匹配 ENTSSO 管理代理实例中 Microsoft Identity Integration Server (MIIS) 的名称。  
  
 **属性： adma** -定义此 ENTSSO 管理代理实例将使用 Active Directory 管理代理的实例名称。 Active Directory 管理代理提供的 Windows 域名和 Windows 用户映射的名称。 此 Active Directory 管理代理实例的名称必须与 MIIS 中的 Active Directory 管理代理实例的名称匹配。  
  
 **属性： deleteAll** -可选; 默认值是`true`。 如果此值设置为`true`，并且 Windows 标识将被删除，从所有 ENTSSO 应用程序将删除与该 Windows 标识的所有映射。  
  
 **元素：应用程序**-定义 SSO 关联应用程序和外部管理代理之间的关系。 多个`Application`允许的元素。  
  
 **属性： 名称**-定义 SSO 关联应用程序的名称。 此应用程序必须已存在于 ENTSSO 系统。  
  
 **属性： sourceMA** -定义源 （外部） 的实例名称将用于提供此应用程序的映射中的外部 UserId 的管理代理。 此外部管理代理实例的名称必须与 MIIS 中外部 MA 实例的名称匹配。  
  
 **属性： 创建**-可选; 默认值是`true`。 定义是否应为此应用程序创建映射。  
  
 **属性： 删除**-可选; 默认值是`true`。 定义是否应为此应用程序删除映射。  
  
 **元素：SourceMA** -可选。 标识特定源 （外部） 管理代理实例的对象类型和属性名称。 如果此元素不存在特定的管理代理，则的默认对象类型 ("person") 和属性名称 ("uid") 假定。 多个`SourceMA`允许的元素。  
  
 **属性： 名称**-源 （外部） 的名称管理代理。 此名称必须与至少一个`sourceMA`属性名称从`Application`元素。  
  
 **属性： objectType** -可选; 默认值是`person`。 如果提供外部 UserId 的对象类型名称不是`person`，它应在此处指定。  
  
 **属性： 特性**-可选; 默认值是`uid`。 如果提供外部 UserId 的属性名称不是`uid`，可在此处指定它。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 ENTSSO 管理代理](../core/how-to-use-the-entsso-management-agent.md)