---
title: 导出 BizTalk 应用程序、 绑定和策略 |Microsoft 文档
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
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245805"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="91de4-102">导出 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="91de4-102">Exporting BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="91de4-103">本部分介绍如何导出 BizTalk 应用程序、绑定或策略。</span><span class="sxs-lookup"><span data-stu-id="91de4-103">This section describes how to export a BizTalk application, bindings, or policies.</span></span> <span data-ttu-id="91de4-104">可以导出在某一 BizTalk 应用程序中包含的某些或所有项目，也可以只导出该应用程序的绑定或策略。</span><span class="sxs-lookup"><span data-stu-id="91de4-104">You can export some or all of the artifacts contained in a BizTalk application, or you can export only its bindings or policies.</span></span> <span data-ttu-id="91de4-105">导出 BizTalk 应用程序会创建一个 Windows Installer (.msi) 文件，该文件包含您选择导出的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="91de4-105">Exporting an application creates a Windows Installer (.msi) file containing the application artifacts that you selected for export.</span></span> <span data-ttu-id="91de4-106">导出绑定或策略将创建一个包含这些绑定或策略的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="91de4-106">Exporting bindings or policies creates an .xml file of the bindings or policies.</span></span> <span data-ttu-id="91de4-107">此过程的背景信息，请参阅[什么发生时项目导出](../core/what-happens-when-artifacts-are-exported.md)。</span><span class="sxs-lookup"><span data-stu-id="91de4-107">For background information on this process, see [What Happens When Artifacts Are Exported](../core/what-happens-when-artifacts-are-exported.md).</span></span>  
  
 <span data-ttu-id="91de4-108">您可以将某一应用程序 .msi 文件导入其他 BizTalk 组，以便在该组中创建包含该应用程序项目的新应用程序。</span><span class="sxs-lookup"><span data-stu-id="91de4-108">You can import an application .msi file into another BizTalk group to create a new application that contains the application's artifacts in that group.</span></span> <span data-ttu-id="91de4-109">您可以将某一绑定或策略 .xml 文件导入其他 BizTalk 应用程序，以便使用这些绑定或策略。</span><span class="sxs-lookup"><span data-stu-id="91de4-109">You can import a binding or policy .xml file into another BizTalk application to use the bindings or policies.</span></span> <span data-ttu-id="91de4-110">中介绍了如何导入项目[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="91de4-110">How to import artifacts is described in [Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91de4-111">请将绑定文件存储于安全的位置，因为它们可能包含连接和配置信息之类的重要业务数据。</span><span class="sxs-lookup"><span data-stu-id="91de4-111">Store binding files in a secure location, as they may contain critical business data such as connectivity and configuration information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91de4-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="91de4-112">In This Section</span></span>  
  
-   [<span data-ttu-id="91de4-113">如何导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="91de4-113">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)  
  
-   [<span data-ttu-id="91de4-114">导出绑定</span><span class="sxs-lookup"><span data-stu-id="91de4-114">Exporting Bindings</span></span>](../core/exporting-bindings6.md)  
  
-   [<span data-ttu-id="91de4-115">如何导出策略</span><span class="sxs-lookup"><span data-stu-id="91de4-115">How to Export a Policy</span></span>](../core/how-to-export-a-policy.md)