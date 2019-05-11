---
title: 导出 BizTalk 应用程序、 绑定和策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1847834ee04cf6b5f1d60398ea4310cac60b53c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388239"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="d2e5d-102">导出 BizTalk 应用程序、 绑定和策略</span><span class="sxs-lookup"><span data-stu-id="d2e5d-102">Exporting BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="d2e5d-103">本部分介绍如何导出 BizTalk 应用程序、 绑定或策略。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-103">This section describes how to export a BizTalk application, bindings, or policies.</span></span> <span data-ttu-id="d2e5d-104">您可以导出某些或所有包含 BizTalk 应用程序中的项目也可以导出的绑定或策略。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-104">You can export some or all of the artifacts contained in a BizTalk application, or you can export only its bindings or policies.</span></span> <span data-ttu-id="d2e5d-105">导出应用程序创建包含应用程序项目，选择要导出的 Windows Installer (.msi) 文件。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-105">Exporting an application creates a Windows Installer (.msi) file containing the application artifacts that you selected for export.</span></span> <span data-ttu-id="d2e5d-106">导出绑定或策略创建绑定或策略.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-106">Exporting bindings or policies creates an .xml file of the bindings or policies.</span></span> <span data-ttu-id="d2e5d-107">此过程的背景信息，请参阅[什么会发生在项目将导出](../core/what-happens-when-artifacts-are-exported.md)。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-107">For background information on this process, see [What Happens When Artifacts Are Exported](../core/what-happens-when-artifacts-are-exported.md).</span></span>  
  
 <span data-ttu-id="d2e5d-108">您可以导入其他 BizTalk 组中创建新的应用程序包含在该组中的应用程序的项目的应用程序.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-108">You can import an application .msi file into another BizTalk group to create a new application that contains the application's artifacts in that group.</span></span> <span data-ttu-id="d2e5d-109">您可以导入另一个 BizTalk 应用程序使用这些绑定或策略的绑定或策略.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-109">You can import a binding or policy .xml file into another BizTalk application to use the bindings or policies.</span></span> <span data-ttu-id="d2e5d-110">如何导入项目所述[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-110">How to import artifacts is described in [Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e5d-111">将绑定文件存储在安全位置，因为它们可能包含连接和配置信息之类的关键业务数据。</span><span class="sxs-lookup"><span data-stu-id="d2e5d-111">Store binding files in a secure location, as they may contain critical business data such as connectivity and configuration information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2e5d-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="d2e5d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d2e5d-113">如何导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2e5d-113">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)  
  
-   [<span data-ttu-id="d2e5d-114">导出绑定</span><span class="sxs-lookup"><span data-stu-id="d2e5d-114">Exporting Bindings</span></span>](../core/exporting-bindings6.md)  
  
-   [<span data-ttu-id="d2e5d-115">如何导出策略</span><span class="sxs-lookup"><span data-stu-id="d2e5d-115">How to Export a Policy</span></span>](../core/how-to-export-a-policy.md)