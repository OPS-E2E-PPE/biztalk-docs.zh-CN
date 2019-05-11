---
title: MT 消息示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6406a5d1e11ddeefd0aeb86c0d350acf5892361
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378035"
---
# <a name="examples-of-mt-messages"></a><span data-ttu-id="80b5a-102">MT 消息示例</span><span class="sxs-lookup"><span data-stu-id="80b5a-102">Examples of MT Messages</span></span>
<span data-ttu-id="80b5a-103">**要生成不同的 MT 消息的解决方案 （InfoPath 窗体模板） 的命令：**</span><span class="sxs-lookup"><span data-stu-id="80b5a-103">**Commands to generate the solution (InfoPath form template) for the Different MT messages:**</span></span>  
  
 <span data-ttu-id="80b5a-104">以下示例要求"SWIFT 基本 Types.xsd"、"SWIFT 常见数据 Types.xsd","MT102.xsd"、"MT500.xsd"和"MT103.xsd"架构都在 c:\schemas。</span><span class="sxs-lookup"><span data-stu-id="80b5a-104">The following examples require that the "SWIFT Base Types.xsd", "SWIFT Common Data Types.xsd","MT102.xsd", "MT500.xsd", and "MT103.xsd" schemas are all in c:\schemas.</span></span> <span data-ttu-id="80b5a-105">这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="80b5a-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="80b5a-106">该解决方案的文件夹名称会与 InfoPath 窗体需要生成的消息的名称相同。</span><span class="sxs-lookup"><span data-stu-id="80b5a-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="80b5a-107">这些示例假定该实用程序已被放入"C:\FormGeneratorUtility2008"文件夹。</span><span class="sxs-lookup"><span data-stu-id="80b5a-107">These examples assume that the utility has been placed in “C:\FormGeneratorUtility2008” folder.</span></span> <span data-ttu-id="80b5a-108">中的实用程序为所选的位置替换为下面的命令。</span><span class="sxs-lookup"><span data-stu-id="80b5a-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="80b5a-109">**若要生成用于 MT103 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="80b5a-109">**To generate a form for the MT103 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   <span data-ttu-id="80b5a-110">**若要生成用于 MT103、 MT102 和 MT500 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="80b5a-110">**To generate a form for the MT103, MT102, and MT500 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   <span data-ttu-id="80b5a-111">**若要生成用于 MT103 架构 （来自文件） 的窗体：**</span><span class="sxs-lookup"><span data-stu-id="80b5a-111">**To generate a form for the MT103 schema (from the file):**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`