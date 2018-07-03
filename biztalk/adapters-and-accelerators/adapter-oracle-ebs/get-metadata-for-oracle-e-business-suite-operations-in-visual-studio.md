---
title: 获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据 |Microsoft Docs
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
ms.openlocfilehash: 7f4a7b5d016adf1cc7fa8bb73772e1e5d7145520
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002070"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a>获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供三种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助您开发使用该适配器的解决方案的组件：  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  适配器客户端必须使用这些组件连接到 Oracle E-business Suite，然后生成他们想要执行的操作的元数据。 所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：  
  
- 为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。  
  
- 检索由这些目标操作该适配器公开的元数据。  
  
- 转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。  
  
  本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
> [!NOTE]
>  如果已创建特定版本的 Oracle E-business Suite 上使用该适配器的解决方案，现在想要部署在不同版本的 Oracle E-business Suite 解决方案然后应将其部署之前测试解决方案。 因为基础项目的元数据可能会不同部署上的 Oracle E-business Suite 的不同版本的解决方案时，可能会遇到问题。 若要解决此问题，应重新生成在相同版本的 Oracle E-business Suite 你想要部署该解决方案使用的适配器的元数据。  
  
