---
title: 步骤 4：创建示例 XML BeginDoc2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cdda509-085f-4485-b488-c045d589ee96
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eea7067581391404fbb9c61afc5c340ec26d05e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392528"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="f1573-102">步骤 4：创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="f1573-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="f1573-103">将以下代码保存到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f1573-103">Save the following code into an XML file.</span></span> <span data-ttu-id="f1573-104">如果你的测试在此示例中，使用的步骤，并使用示例的 j.d.</span><span class="sxs-lookup"><span data-stu-id="f1573-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="f1573-105">Edwards EnterpriseOne 对象选择 [jde: //csales/b4200310]，您可以拖放到输入文件夹并查看指定 Out 文件夹 （该文件夹绑定到 EndDocOut 端口）。</span><span class="sxs-lookup"><span data-stu-id="f1573-105">Edwards EnterpriseOne object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1573-106">您必须修改某些值以指向您的 j.d.</span><span class="sxs-lookup"><span data-stu-id="f1573-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="f1573-107">Edwards EnterpriseOne 服务器，例如，szCMComputerID 中设置。</span><span class="sxs-lookup"><span data-stu-id="f1573-107">Edwards EnterpriseOne server, for example, the value set in szCMComputerID.</span></span>  
  
```  
<ns0:F4211FSBeginDoc xmlns:ns0="http://schemas.microsoft.com/  
      [JDE://CSALES/B4200310]">  
   <ns0:mnCMJobNumber></ns0:mnCMJobNumber>  
   <ns0:cCMDocAction>A</ns0:cCMDocAction>  
   <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
   <ns0:szCMComputerID>BVISION02</ns0:szCMComputerID>  
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
  
## <a name="see-also"></a><span data-ttu-id="f1573-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1573-108">See Also</span></span>  
 <span data-ttu-id="f1573-109">[步骤 1：引用架构 DLL](../core/step-1-reference-the-schema-dll1.md) </span><span class="sxs-lookup"><span data-stu-id="f1573-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll1.md) </span></span>  
 <span data-ttu-id="f1573-110">[步骤 2：创建业务流程](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="f1573-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 [<span data-ttu-id="f1573-111">步骤 3：完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="f1573-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)