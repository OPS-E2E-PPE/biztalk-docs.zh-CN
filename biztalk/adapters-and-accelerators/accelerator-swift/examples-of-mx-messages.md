---
title: MX 消息示例 |Microsoft Docs
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
ms.openlocfilehash: 26d86af52d8f93986d7028977166df8cfb28045c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377887"
---
# <a name="examples-of-mx-messages"></a><span data-ttu-id="ba400-102">MX 消息示例</span><span class="sxs-lookup"><span data-stu-id="ba400-102">Examples of MX Messages</span></span>
<span data-ttu-id="ba400-103">命令行以生成不同 MX 消息的解决方案 （InfoPath 窗体模板）</span><span class="sxs-lookup"><span data-stu-id="ba400-103">Command Lines to generate the solution (InfoPath form template) for the Different MX messages</span></span>  
  
 <span data-ttu-id="ba400-104">以下示例要求在架构"pacs.004.001.01"和"pain.002.001.01"架构都在 c:\schemas。</span><span class="sxs-lookup"><span data-stu-id="ba400-104">The following examples require that the “pacs.004.001.01" and “pain.002.001.01” schemas are all in c:\schemas.</span></span> <span data-ttu-id="ba400-105">这将为"C:\GeneratedForms"文件夹中的 InfoPath 窗体模板生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba400-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="ba400-106">该解决方案的文件夹名称会与 InfoPath 窗体需要生成的消息的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ba400-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="ba400-107">这些示例假定该实用程序已被放入"C:\Program Files\Microsoft BizTalk Accelerator 的 SWIFT\SDK\FormGeneratorUtility"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ba400-107">These examples assume that the utility has been placed in “C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\FormGeneratorUtility” folder.</span></span> <span data-ttu-id="ba400-108">中的实用程序为所选的位置替换为下面的命令。</span><span class="sxs-lookup"><span data-stu-id="ba400-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="ba400-109">**若要生成用于 pacs.004.001.01 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="ba400-109">**To generate a form for the pacs.004.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   <span data-ttu-id="ba400-110">**若要生成用于 pacs.004.001.01 和 pain.002.001.01 架构的窗体：**</span><span class="sxs-lookup"><span data-stu-id="ba400-110">**To generate a form for the pacs.004.001.01 and pain.002.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`