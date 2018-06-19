---
title: 步骤 4： 创建示例 XML BeginDoc2 |Microsoft 文档
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
ms.openlocfilehash: 65598296f7136dc47c747165c9f7aba20602be4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277533"
---
# <a name="step-4-create-a-sample-xml-begindoc"></a><span data-ttu-id="751fe-102">步骤 4： 创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="751fe-102">Step 4: Create a Sample XML BeginDoc</span></span>
<span data-ttu-id="751fe-103">将以下代码保存到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="751fe-103">Save the following code into an XML file.</span></span> <span data-ttu-id="751fe-104">如果您的测试使用本例中的步骤，并且使用示例的 J.D.</span><span class="sxs-lookup"><span data-stu-id="751fe-104">If your test uses the steps in this example, and uses the example's J.D.</span></span> <span data-ttu-id="751fe-105">Edwards EnterpriseOne 对象选择 [JDE://CSALES/B4200310]，可以将其拖放到“输入”文件夹并查看指定的“输出”文件夹（该文件夹绑定到 EndDocOut 端口）中会出现什么内容。</span><span class="sxs-lookup"><span data-stu-id="751fe-105">Edwards EnterpriseOne object selection, [JDE://CSALES/B4200310], you can drop this into the Input folder and what it come out the designated Out folder (the folder bound to the EndDocOut port).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="751fe-106">您必须修改某些值，使其指向您的 J.D.</span><span class="sxs-lookup"><span data-stu-id="751fe-106">You will have to modify some of the values to point to your J.D.</span></span> <span data-ttu-id="751fe-107">Edwards EnterpriseOne 服务器，例如，在 szCMComputerID 中设置的值。</span><span class="sxs-lookup"><span data-stu-id="751fe-107">Edwards EnterpriseOne server, for example, the value set in szCMComputerID.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="751fe-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="751fe-108">See Also</span></span>  
 <span data-ttu-id="751fe-109">[步骤 1： 引用 DLL 的架构](../core/step-1-reference-the-schema-dll1.md) </span><span class="sxs-lookup"><span data-stu-id="751fe-109">[Step 1: Reference the Schema DLL](../core/step-1-reference-the-schema-dll1.md) </span></span>  
 <span data-ttu-id="751fe-110">[步骤 2： 创建业务流程](../core/step-2-create-the-orchestration2.md) </span><span class="sxs-lookup"><span data-stu-id="751fe-110">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration2.md) </span></span>  
 [<span data-ttu-id="751fe-111">步骤 3： 完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="751fe-111">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)