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
ms.openlocfilehash: 77977351036e86e558491a2c2927a29878ae550b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375530"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a><span data-ttu-id="87988-102">获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="87988-102">Get metadata for Oracle E-Business Suite operations in Visual Studio</span></span>
<span data-ttu-id="87988-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供三种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助您开发使用该适配器的解决方案的组件：</span><span class="sxs-lookup"><span data-stu-id="87988-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter:</span></span>  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  <span data-ttu-id="87988-104">适配器客户端必须使用这些组件连接到 Oracle E-business Suite，然后生成他们想要执行的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="87988-104">Adapter clients must use these components to connect to Oracle E-Business Suite, and then generate metadata for the operations they want to perform.</span></span> <span data-ttu-id="87988-105">所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：</span><span class="sxs-lookup"><span data-stu-id="87988-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="87988-106">为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。</span><span class="sxs-lookup"><span data-stu-id="87988-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="87988-107">检索由这些目标操作该适配器公开的元数据。</span><span class="sxs-lookup"><span data-stu-id="87988-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="87988-108">转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="87988-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="87988-109">本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="87988-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87988-110">如果已创建特定版本的 Oracle E-business Suite 上使用该适配器的解决方案，现在想要部署在不同版本的 Oracle E-business Suite 解决方案然后应将其部署之前测试解决方案。</span><span class="sxs-lookup"><span data-stu-id="87988-110">If you have created a solution using the adapter on a particular version of Oracle E-Business Suite, and now want to deploy the solution on a different version of Oracle E-Business Suite then you should test the solution before deploying it.</span></span> <span data-ttu-id="87988-111">因为基础项目的元数据可能会不同部署上的 Oracle E-business Suite 的不同版本的解决方案时，可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="87988-111">You might face issues while deploying the solution on a different version of Oracle E-Business Suite because the metadata of the underlying artifact might be different.</span></span> <span data-ttu-id="87988-112">若要解决此问题，应重新生成在相同版本的 Oracle E-business Suite 你想要部署该解决方案使用的适配器的元数据。</span><span class="sxs-lookup"><span data-stu-id="87988-112">To resolve this issue, you should regenerate the metadata using the adapter on the same version of Oracle E-Business Suite on which you intend to deploy the solution.</span></span>  
  
