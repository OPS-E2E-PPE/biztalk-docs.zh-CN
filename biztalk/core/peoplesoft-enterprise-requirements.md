---
title: "PeopleSoft 企业要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft Enterprise, requirements
- send handlers, PeopleSoft requirements
- CLASSPATH environment variable
- custom component interface object
- system requirements
- GET_CI_INFO.pc
ms.assetid: fabd808d-d9b6-43b0-a12a-727189f00a9d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f267afce09e9c50d732d376fde43beaa1ef39a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="b8f09-102">PeopleSoft Enterprise 要求</span><span class="sxs-lookup"><span data-stu-id="b8f09-102">PeopleSoft Enterprise Requirements</span></span>
## <a name="send-handler-peoplesoft-requirements"></a><span data-ttu-id="b8f09-103">发送处理程序 PeopleSoft 要求</span><span class="sxs-lookup"><span data-stu-id="b8f09-103">Send Handler PeopleSoft Requirements</span></span>  
 <span data-ttu-id="b8f09-104">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器包含一个自定义组件接口 (CI) 并且可以通过 Java API 对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="b8f09-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="b8f09-105">使用 PeopleSoft 工具在 PeopleSoft 系统中部署一个自定义 CI 对象 `GET_CI_INFO`，以提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息。</span><span class="sxs-lookup"><span data-stu-id="b8f09-105">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="b8f09-106">有关详细信息，请参阅[准备使用 PeopleSoft 企业](../core/preparing-to-use-peoplesoft-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f09-106">For more information, see [Preparing to Use PeopleSoft Enterprise](../core/preparing-to-use-peoplesoft-enterprise.md).</span></span>  
  
 <span data-ttu-id="b8f09-107">上载自定义组件接口是一次性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b8f09-107">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="b8f09-108">该文件 `GET_CI_INFO.pc` 是与产品一起安装的，并且必须安装该文件才能使用该适配器来浏览 CI。</span><span class="sxs-lookup"><span data-stu-id="b8f09-108">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="b8f09-109">您必须拥有对 PeopleSoft 应用程序设计器的访问权限，但应用程序设计器应用程序不必位于 BizTalk Server 计算机上。</span><span class="sxs-lookup"><span data-stu-id="b8f09-109">You must have access to the PeopleSoft Application Designer, but the Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="b8f09-110">您可以使用此应用程序设计器将自定义 CI 上载到您浏览的 PeopleSoft 计算机上。</span><span class="sxs-lookup"><span data-stu-id="b8f09-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="b8f09-111">因为你必须设置此环境变量类路径中，你必须有权 PeopleSoft 计算机 (或设置中的信息**传输属性**屏幕) 以指向 PeopleSoft 的`PSJOA/psjoa.jar`文件。</span><span class="sxs-lookup"><span data-stu-id="b8f09-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f09-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8f09-112">See Also</span></span>  
 <span data-ttu-id="b8f09-113">[入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="b8f09-113">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="b8f09-114">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="b8f09-114">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)