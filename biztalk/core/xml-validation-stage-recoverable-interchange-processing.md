---
title: XML 验证阶段 （可恢复的交换处理） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8f0225e100053fe6dced8165b7fc800c5e4804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289949"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a><span data-ttu-id="d4d91-102">XML 验证阶段（可恢复的交换处理)</span><span class="sxs-lookup"><span data-stu-id="d4d91-102">XML Validation Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="d4d91-103">**XML 验证器**管道组件处理以下两种模式的交换：</span><span class="sxs-lookup"><span data-stu-id="d4d91-103">The **XML validator** pipeline component processes an interchange in two modes:</span></span>  
  
-   <span data-ttu-id="d4d91-104">**标准模式**。</span><span class="sxs-lookup"><span data-stu-id="d4d91-104">**Standard mode**.</span></span> <span data-ttu-id="d4d91-105">当**XML 验证器**组件配置为执行标准的验证，将交换中包含的消息验证事务工作单元中。</span><span class="sxs-lookup"><span data-stu-id="d4d91-105">When the **XML validator** component is configured to perform standard validation, the messages contained in an interchange are validated in a transactional unit of work.</span></span> <span data-ttu-id="d4d91-106">特殊情况下，如果交换中的消息验证失败，则整个交换（包含所有消息）将会被放在挂起的队列中。</span><span class="sxs-lookup"><span data-stu-id="d4d91-106">Specifically, if validation of a message in the interchange fails, the entire interchange (containing all the messages) is placed in the suspended queue.</span></span>  
  
-   <span data-ttu-id="d4d91-107">**可恢复模式**。</span><span class="sxs-lookup"><span data-stu-id="d4d91-107">**Recoverable mode**.</span></span> <span data-ttu-id="d4d91-108">当**XML 验证器**组件配置处理可恢复的交换，失败时要执行消息验证，该消息会放在挂起的队列和**XML 验证器**组件将继续验证交换中的剩余消息。</span><span class="sxs-lookup"><span data-stu-id="d4d91-108">When the **XML validator** component is configured to perform recoverable interchange processing, if validation of a message fails, the message is placed in the suspended queue and the **XML validator** component continues to validate remaining messages in the interchange.</span></span>  
  
### <a name="to-configure-recoverable-interchange-processing"></a><span data-ttu-id="d4d91-109">若要配置可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="d4d91-109">To configure recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="d4d91-110">在 Visual Studio 中使用管道设计器打开接收管道。</span><span class="sxs-lookup"><span data-stu-id="d4d91-110">Open a receive pipeline by using pipeline designer in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d4d91-111">拖动**XML 验证器**组件从**工具箱**到**验证**接收管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="d4d91-111">Drag **XML validator** component from the **Toolbox** to the **Validate** stage of the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="d4d91-112">在属性窗口中，将的值设置**可恢复交换处理**属性**True**如果你想**XML 验证器**组件与过程的交换在恢复模式下，或将属性设置为**False**如果你想要处理在标准模式下的交换的组件。</span><span class="sxs-lookup"><span data-stu-id="d4d91-112">In the Properties window, set the value of the **Recoverable Interchange Processing** property to **True** if you want the **XML validator** component to process interchanges in the recoverable mode, or set the property to **False** if you want the component to process interchanges in the standard mode.</span></span> <span data-ttu-id="d4d91-113">此属性的默认值是`False`。</span><span class="sxs-lookup"><span data-stu-id="d4d91-113">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="d4d91-114">**XMLValidator**在对象模型中，对应于类**XML 验证器**管道组件，具有名为的公共属性**RecoverableInterchangeProcessing**，你可以使用用于以编程方式获取/设置模式。</span><span class="sxs-lookup"><span data-stu-id="d4d91-114">The **XMLValidator** class in the object model, which corresponds to the **XML validator** pipeline component, has a public property named **RecoverableInterchangeProcessing** that you can use to get/set the mode programmatically.</span></span> <span data-ttu-id="d4d91-115">请参阅文档[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)有关详细信息的类。</span><span class="sxs-lookup"><span data-stu-id="d4d91-115">See documentation for [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) class for more information.</span></span>  
  
 <span data-ttu-id="d4d91-116">成功验证的消息会根据为用于接收父交换的接收端口配置的参与方，来识别其发送方。</span><span class="sxs-lookup"><span data-stu-id="d4d91-116">Messages that are successfully validated have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="d4d91-117">如果参与方解析对从交换提取的任何消息都失败，则认为参与方解析对于整个交换失败。</span><span class="sxs-lookup"><span data-stu-id="d4d91-117">If party resolution for any message extracted from the interchange fails, then the party resolution is considered to have failed for the entire interchange.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d91-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4d91-118">See Also</span></span>  
 [<span data-ttu-id="d4d91-119">如何将 XML 验证程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="d4d91-119">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)