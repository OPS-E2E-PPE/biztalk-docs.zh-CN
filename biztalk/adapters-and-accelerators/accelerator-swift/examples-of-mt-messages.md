---
title: MT 消息的示例 |Microsoft 文档
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
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208885"
---
# <a name="examples-of-mt-messages"></a><span data-ttu-id="87783-102">MT 消息的示例</span><span class="sxs-lookup"><span data-stu-id="87783-102">Examples of MT Messages</span></span>
<span data-ttu-id="87783-103">**用于生成不同 MT 消息的解决方案 （InfoPath 表单模板） 的命令：**</span><span class="sxs-lookup"><span data-stu-id="87783-103">**Commands to generate the solution (InfoPath form template) for the Different MT messages:**</span></span>  
  
 <span data-ttu-id="87783-104">下面的示例需要"SWIFT 基 Types.xsd"、"SWIFT 常见数据 Types.xsd","MT102.xsd"、"MT500.xsd"和"MT103.xsd"架构都位于 c:\schemas。</span><span class="sxs-lookup"><span data-stu-id="87783-104">The following examples require that the "SWIFT Base Types.xsd", "SWIFT Common Data Types.xsd","MT102.xsd", "MT500.xsd", and "MT103.xsd" schemas are all in c:\schemas.</span></span> <span data-ttu-id="87783-105">这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="87783-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="87783-106">解决方案的文件夹名称将与为其 InfoPath 窗体需要为其生成的消息的名称相同。</span><span class="sxs-lookup"><span data-stu-id="87783-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="87783-107">这些示例假定已置于"C:\FormGeneratorUtility2008"文件夹上的实用工具。</span><span class="sxs-lookup"><span data-stu-id="87783-107">These examples assume that the utility has been placed in “C:\FormGeneratorUtility2008” folder.</span></span> <span data-ttu-id="87783-108">将你选择用于的实用程序中的位置下面的命令。</span><span class="sxs-lookup"><span data-stu-id="87783-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="87783-109">**若要生成用于 MT103 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="87783-109">**To generate a form for the MT103 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   <span data-ttu-id="87783-110">**若要生成用于 MT103、 MT102 和 MT500 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="87783-110">**To generate a form for the MT103, MT102, and MT500 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   <span data-ttu-id="87783-111">**若要生成用于 MT103 架构 （来自文件） 的窗体：**</span><span class="sxs-lookup"><span data-stu-id="87783-111">**To generate a form for the MT103 schema (from the file):**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`