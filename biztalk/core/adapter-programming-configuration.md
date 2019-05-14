---
title: 适配器编程配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b407c6f0239798110b7b971ffa4febd58d6f70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361335"
---
# <a name="adapter-programming-configuration"></a><span data-ttu-id="4d7fa-102">适配器编程配置</span><span class="sxs-lookup"><span data-stu-id="4d7fa-102">Adapter Programming Configuration</span></span>
<span data-ttu-id="4d7fa-103">每种类型的密码同步适配器具有不同的配置要求，具体取决于设计适配器所针对的哪些非 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-103">Every type of password sync adapter has different configuration requirements, depending on what non-Windows system you design the adapter for.</span></span> <span data-ttu-id="4d7fa-104">关联应用程序，正如可以使用企业单一登录配置存储区来集中和更安全地存储配置属性。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-104">Like affiliate applications, you can use the Enterprise Single Sign-On configuration store to store configuration properties centrally and more securely.</span></span>  
  
 <span data-ttu-id="4d7fa-105">如使用其他配置存储应用程序，管理员可以使用企业单一登录管理用户界面来查找和读取描述您的适配器的配置属性的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-105">As with other configuration store applications, an administrator can use the Enterprise Single Sign-On management user interface to locate and read an XML file that describes the configuration properties for your adapter.</span></span> <span data-ttu-id="4d7fa-106">管理工具使用 XML 文件呈现属性页来收集所需的属性值，指定的适配器。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-106">The management tools use the XML file to render a property page to gather the required property values, for the specified adapter.</span></span> <span data-ttu-id="4d7fa-107">此外可以使用 ISSOConfigStore 加载和读取 XML 名称/值组合到和从配置存储区，或者可以使用 SSOPS 工具。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-107">You can also use ISSOConfigStore to load and read XML name/value combinations to and from the configuration store, or you can use the SSOPS tool.</span></span>  
  
 <span data-ttu-id="4d7fa-108">此外可以使用企业单一登录管理工具来启用和禁用适配器。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-108">You can also use the Enterprise Single Sign-On administration tools to enable and disable an adapter.</span></span> <span data-ttu-id="4d7fa-109">在初始创建时，适配器处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4d7fa-109">On initial creation, an adapter is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7fa-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d7fa-110">See Also</span></span>  
 [<span data-ttu-id="4d7fa-111">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="4d7fa-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)