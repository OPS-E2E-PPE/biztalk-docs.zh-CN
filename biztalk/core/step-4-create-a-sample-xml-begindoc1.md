---
title: 步骤 4：创建示例 XML BeginDoc1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e494b4b2-4c83-4293-8ae8-acae29018e7f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeb6f16d6fac0f8d6351ac412583e68d26f2bf15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392567"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="3c345-102">步骤 4：创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="3c345-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="3c345-103">保存将以下内容的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3c345-103">Save the following into an XML file.</span></span> <span data-ttu-id="3c345-104">如果你的测试在此示例中，使用的步骤，并使用示例的 j.d.</span><span class="sxs-lookup"><span data-stu-id="3c345-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="3c345-105">Edwards OneWorld 对象选择 [jde: //csales/b4200310]，您可以拖放到输入文件夹并查看指定 Out 文件夹 （该文件夹绑定到 EndDocOut 端口）。</span><span class="sxs-lookup"><span data-stu-id="3c345-105">Edwards OneWorld object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c345-106">您必须修改某些值以指向您的 j.d.</span><span class="sxs-lookup"><span data-stu-id="3c345-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="3c345-107">Edwards OneWorld 服务器，例如，szCMComputerID 中设置。</span><span class="sxs-lookup"><span data-stu-id="3c345-107">Edwards OneWorld server, for example, the value set in szCMComputerID.</span></span>  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
   [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION01</ns0:szCMComputerID>  
   <ns0:cCMUpdateWriteToWF>2</ns0:cCMUpdateWriteToWF>  
   <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
   <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   <ns0:szOrderType>SO</ns0:szOrderType>  
   <ns0:szBusinessUnit>M30</ns0:szBusinessUnit>  
   <ns0:szOriginalOrderCo></ns0:szOriginalOrderCo>  
   <ns0:szOriginalOrderNo></ns0:szOriginalOrderNo>  
   <ns0:szOriginalOrderType></ns0:szOriginalOrderType>  
   <ns0:mnAddressNumber>1001</ns0:mnAddressNumber>  
   <ns0:jdOrderDate></ns0:jdOrderDate>  
   <ns0:szReference></ns0:szReference>  
   <ns0:cApplyFreightYN>Y</ns0:cApplyFreightYN>  
   <ns0:szCurrencyCode></ns0:szCurrencyCode>  
   <ns0:cWKSourceOfData></ns0:cWKSourceOfData>  
   <ns0:cWKProcMode></ns0:cWKProcMode>  
   <ns0:mnWKSuppressProcess>0</ns0:mnWKSuppressProcess>  
   <ns0:cRetrieveOrderNo>1</ns0:cRetrieveOrderNo>  
   <ns0:nSourceOfOrder>0</ns0:nSourceOfOrder>  
</ns0:F4211FSBeginDoc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c345-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c345-108">See Also</span></span>  
 <span data-ttu-id="3c345-109">[步骤 1：引用架构 DLL](../core/step-1-reference-the-schema-dll2.md) </span><span class="sxs-lookup"><span data-stu-id="3c345-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll2.md) </span></span>  
 <span data-ttu-id="3c345-110">[步骤 2：创建业务流程](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="3c345-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 [<span data-ttu-id="3c345-111">步骤 3：完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="3c345-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)