---
title: 自定义绑定文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74322134891c7f52f9892d4c658d897fb95f9305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390012"
---
# <a name="customizing-binding-files"></a><span data-ttu-id="fa982-102">自定义绑定文件</span><span class="sxs-lookup"><span data-stu-id="fa982-102">Customizing Binding Files</span></span>
<span data-ttu-id="fa982-103">绑定文件是描述 BizTalk 管理数据库和这些项目之间的关系中的项目的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fa982-103">Binding files are XML files that describe artifacts in a BizTalk Management database and the relationship between these artifacts.</span></span> <span data-ttu-id="fa982-104">绑定文件可用于从一个 BizTalk 配置数据库中导出配置信息并导入另一个 BizTalk 配置数据库的此信息。</span><span class="sxs-lookup"><span data-stu-id="fa982-104">Binding files are useful for exporting configuration information from one BizTalk configuration database and importing this information into another BizTalk configuration database.</span></span> <span data-ttu-id="fa982-105">例如，开发人员可能设计一个 BizTalk 解决方案，并在开发环境中，及其相关的项目，然后将这些项目导出到绑定文件和最后，这些项目导入到生产环境。</span><span class="sxs-lookup"><span data-stu-id="fa982-105">For example, a developer may design a BizTalk solution and its related artifacts in a development environment, then export these artifacts to a binding file and finally, import these artifacts into a production environment.</span></span> <span data-ttu-id="fa982-106">绑定文件还可用于更新现有配置。</span><span class="sxs-lookup"><span data-stu-id="fa982-106">You can also use a binding file to update an existing configuration.</span></span> <span data-ttu-id="fa982-107">例如可以应用与绑定文件一起在开发环境与生产环境中进行的配置更改。</span><span class="sxs-lookup"><span data-stu-id="fa982-107">For example you can apply configuration changes made in a development environment to your production environment with a binding file.</span></span> <span data-ttu-id="fa982-108">更新现有配置与绑定文件中，绑定文件，并可以在绑定文件中设置的适配器特定的配置属性的结构时，本主题讨论的注意事项。</span><span class="sxs-lookup"><span data-stu-id="fa982-108">This topic discusses considerations when updating an existing configuration with a binding file, the structure of a binding file, and adapter specific configuration properties that can be set in a binding file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa982-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="fa982-109">In This Section</span></span>  
  
-   [<span data-ttu-id="fa982-110">使用绑定文件更新现有配置</span><span class="sxs-lookup"><span data-stu-id="fa982-110">Updating an Existing Configuration with a Binding File</span></span>](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [<span data-ttu-id="fa982-111">绑定文件的结构</span><span class="sxs-lookup"><span data-stu-id="fa982-111">Structure of a Binding File</span></span>](../core/structure-of-a-binding-file.md)  
  
-   [<span data-ttu-id="fa982-112">配置集成的 BizTalk 适配器的属性</span><span class="sxs-lookup"><span data-stu-id="fa982-112">Configuration Properties for Integrated BizTalk Adapters</span></span>](../core/configuration-properties-for-integrated-biztalk-adapters.md)