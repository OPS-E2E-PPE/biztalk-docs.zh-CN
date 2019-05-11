---
title: 如何验证实例消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb7d83c8ba847a84a38b2701bb5ca2492559d450
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333182"
---
# <a name="how-to-validate-instance-messages"></a><span data-ttu-id="84991-102">如何验证实例消息</span><span class="sxs-lookup"><span data-stu-id="84991-102">How to Validate Instance Messages</span></span>
<span data-ttu-id="84991-103">构造架构之后，可以通过验证您知道此类实例消息的架构很好地反映现有实例消息中检查您的工作。</span><span class="sxs-lookup"><span data-stu-id="84991-103">After you have constructed a schema, you can check your work by validating a pre-existing instance message that you know is a good representation of such instance messages against the schema.</span></span>  
  
 <span data-ttu-id="84991-104">本主题提供执行此验证任务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="84991-104">This topic provides step-by-step instructions for this validation task.</span></span>  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a><span data-ttu-id="84991-105">若要验证针对架构的实例消息</span><span class="sxs-lookup"><span data-stu-id="84991-105">To validate an instance message against a schema</span></span>  
  
1.  <span data-ttu-id="84991-106">在解决方案资源管理器，右键单击该架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="84991-106">In Solution Explorer, right-click the schema, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="84991-107">如有必要，在属性窗口中，展开**常规**一部分**常规**选项卡上，通过单击其加号 （+） 图标。</span><span class="sxs-lookup"><span data-stu-id="84991-107">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="84991-108">在中**输入实例文件名**属性值字段中，键入文件的名称，或使用省略号 (**...**) 按钮以浏览到包含要根据架构进行验证，然后单击的实例消息的文件的值字段右侧**打开**。</span><span class="sxs-lookup"><span data-stu-id="84991-108">In the **Input Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file that contains the instance message to be validated against the schema, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="84991-109">在中**解决方案资源管理器**，右键单击架构名称，然后单击**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="84991-109">In **Solution Explorer**, right-click the schema name, and then click **Validate Instance**.</span></span>  
  
5.  <span data-ttu-id="84991-110">在输出窗口中查看结果。</span><span class="sxs-lookup"><span data-stu-id="84991-110">In the Output window, view the results.</span></span> <span data-ttu-id="84991-111">在此窗口中显示成功和错误消息。</span><span class="sxs-lookup"><span data-stu-id="84991-111">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84991-112">有一些情况下实例中的特定架构生成消息可能无法通过使用该相同的架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="84991-112">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="84991-113">有关这种情况下的详细信息，请参阅[架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="84991-113">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="84991-114">通常情况下，想要编辑生成的实例消息并将更改，使其更真实地表示你的方案及其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="84991-114">Generally, you will want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="84991-115">然后使用此修改后的实例消息来验证您的架构。</span><span class="sxs-lookup"><span data-stu-id="84991-115">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84991-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="84991-116">See Also</span></span>  
 <span data-ttu-id="84991-117">[测试架构](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="84991-117">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="84991-118">[架构验证](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="84991-118">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="84991-119">实例消息的生成和验证</span><span class="sxs-lookup"><span data-stu-id="84991-119">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)