---
title: 获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ef4cc308979718f306958d0da1bb1eceaebaf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215037"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a>获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供三种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助你开发使用该适配器的解决方案的组件：  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
-   [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
 适配器客户端必须使用这些组件以连接到 Oracle E-business Suite，然后生成他们想要执行的操作的元数据。 所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化开发：  
  
-   为你想要使用你的解决方案中的操作提供的 Microsoft Windows 界面通过它您可以浏览和搜索。  
  
-   检索由这些目标操作的适配器公开元数据。  
  
-   将转换该元数据，这表示为 Web 服务描述语言 (WSDL) 文档的适配器，到可以 （BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示在解决方案中使用一个窗体服务模型） 并将其添加到你的项目。  
  
 本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
> [!NOTE]
>  如果你已创建使用该适配器上 Oracle E-business Suite 的特定版本的解决方案，现在想要部署在不同版本的 Oracle E-business Suite 解决方案然后应将其部署之前测试解决方案。 在部署上 Oracle E-business Suite 的不同版本的解决方案，因为基础项目的元数据可能不同的过程，你可能面临问题。 若要解决此问题，应重新生成元数据中使用相同版本的 Oracle E-business Suite 你想要部署解决方案上的适配器。  
  
