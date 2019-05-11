---
title: XML 验证阶段 （可恢复的交换处理） |Microsoft Docs
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
ms.openlocfilehash: 5c2aad27b00012972214e2d86ad78a871bb609fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401559"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a><span data-ttu-id="f0d2b-102">XML 验证阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="f0d2b-102">XML Validation Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="f0d2b-103">**XML 验证器**管道组件处理两种模式中的交换：</span><span class="sxs-lookup"><span data-stu-id="f0d2b-103">The **XML validator** pipeline component processes an interchange in two modes:</span></span>  
  
-   <span data-ttu-id="f0d2b-104">**标准模式**。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-104">**Standard mode**.</span></span> <span data-ttu-id="f0d2b-105">当**XML 验证器**组件配置为执行标准验证，将交换中包含的消息进行验证的事务的工作单元。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-105">When the **XML validator** component is configured to perform standard validation, the messages contained in an interchange are validated in a transactional unit of work.</span></span> <span data-ttu-id="f0d2b-106">具体而言，如果交换中的消息验证失败，整个交换 （包含所有消息） 被置于挂起队列。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-106">Specifically, if validation of a message in the interchange fails, the entire interchange (containing all the messages) is placed in the suspended queue.</span></span>  
  
-   <span data-ttu-id="f0d2b-107">**可恢复模式**。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-107">**Recoverable mode**.</span></span> <span data-ttu-id="f0d2b-108">当**XML 验证器**配置组件来执行可恢复交换处理时，如果消息验证失败，消息被放置在挂起队列和**XML 验证器**组件将继续验证交换中的剩余消息。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-108">When the **XML validator** component is configured to perform recoverable interchange processing, if validation of a message fails, the message is placed in the suspended queue and the **XML validator** component continues to validate remaining messages in the interchange.</span></span>  
  
### <a name="to-configure-recoverable-interchange-processing"></a><span data-ttu-id="f0d2b-109">若要配置可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="f0d2b-109">To configure recoverable interchange processing</span></span>  
  
1. <span data-ttu-id="f0d2b-110">在 Visual Studio 中使用管道设计器打开接收管道。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-110">Open a receive pipeline by using pipeline designer in Visual Studio.</span></span>  
  
2. <span data-ttu-id="f0d2b-111">拖动**XML 验证器**组件从**工具箱**到**Validate**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-111">Drag **XML validator** component from the **Toolbox** to the **Validate** stage of the receive pipeline.</span></span>  
  
3. <span data-ttu-id="f0d2b-112">在属性窗口中设置的值**可恢复交换处理**属性设置为**True**如果你想**XML 验证器**组件进程的交换，在可恢复模式下，或将属性设置为**False**如果您希望该组件在标准模式下的交换进行处理。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-112">In the Properties window, set the value of the **Recoverable Interchange Processing** property to **True** if you want the **XML validator** component to process interchanges in the recoverable mode, or set the property to **False** if you want the component to process interchanges in the standard mode.</span></span> <span data-ttu-id="f0d2b-113">此属性的默认值为 `False`。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-113">The default value of this property is `False`.</span></span>  
  
   <span data-ttu-id="f0d2b-114">**器**类在对象模型中，对应于**XML 验证器**管道组件，有一个名为的公共属性**RecoverableInterchangeProcessing**可用来以编程方式获取/设置模式。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-114">The **XMLValidator** class in the object model, which corresponds to the **XML validator** pipeline component, has a public property named **RecoverableInterchangeProcessing** that you can use to get/set the mode programmatically.</span></span> <span data-ttu-id="f0d2b-115">请参阅文档[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)类的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-115">See documentation for [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) class for more information.</span></span>  
  
   <span data-ttu-id="f0d2b-116">已成功验证的消息具有标识为在其相应父交换到达的接收端口配置的参与方根据其发送方。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-116">Messages that are successfully validated have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="f0d2b-117">如果从交换提取的任何消息的参与方解析失败，则认为参与方解析对于整个交换失败。</span><span class="sxs-lookup"><span data-stu-id="f0d2b-117">If party resolution for any message extracted from the interchange fails, then the party resolution is considered to have failed for the entire interchange.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d2b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0d2b-118">See Also</span></span>  
 [<span data-ttu-id="f0d2b-119">如何配置 XML 验证器管道组件</span><span class="sxs-lookup"><span data-stu-id="f0d2b-119">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)