---
title: MX 消息示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5280f8ec2ce16344562907a95c1b0afa8c6627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209141"
---
# <a name="examples-of-mx-messages"></a><span data-ttu-id="f49e4-102">MX 消息的示例</span><span class="sxs-lookup"><span data-stu-id="f49e4-102">Examples of MX Messages</span></span>
<span data-ttu-id="f49e4-103">命令行以生成不同 MX 消息的解决方案 （InfoPath 表单模板）</span><span class="sxs-lookup"><span data-stu-id="f49e4-103">Command Lines to generate the solution (InfoPath form template) for the Different MX messages</span></span>  
  
 <span data-ttu-id="f49e4-104">下面的示例需要的架构"pacs.004.001.01"和"pain.002.001.01"架构都位于 c:\schemas。</span><span class="sxs-lookup"><span data-stu-id="f49e4-104">The following examples require that the “pacs.004.001.01" and “pain.002.001.01” schemas are all in c:\schemas.</span></span> <span data-ttu-id="f49e4-105">这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="f49e4-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="f49e4-106">解决方案的文件夹名称将与为其 InfoPath 窗体需要为其生成的消息的名称相同。</span><span class="sxs-lookup"><span data-stu-id="f49e4-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="f49e4-107">这些示例假定已置于"C:\Program Files\Microsoft BizTalk 快捷键的 SWIFT\SDK\FormGeneratorUtility"文件夹上的实用工具。</span><span class="sxs-lookup"><span data-stu-id="f49e4-107">These examples assume that the utility has been placed in “C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\FormGeneratorUtility” folder.</span></span> <span data-ttu-id="f49e4-108">将你选择用于的实用程序中的位置下面的命令。</span><span class="sxs-lookup"><span data-stu-id="f49e4-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="f49e4-109">**若要生成用于 pacs.004.001.01 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="f49e4-109">**To generate a form for the pacs.004.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   <span data-ttu-id="f49e4-110">**若要生成用于 pacs.004.001.01 和 pain.002.001.01 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="f49e4-110">**To generate a form for the pacs.004.001.01 and pain.002.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`