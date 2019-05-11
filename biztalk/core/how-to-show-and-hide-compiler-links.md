---
title: 如何显示和隐藏编译器链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931d829d37e6fdb594746598164a4b189c75a763
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383878"
---
# <a name="how-to-show-and-hide-compiler-links"></a><span data-ttu-id="8b6c4-102">如何显示和隐藏编译器链接</span><span class="sxs-lookup"><span data-stu-id="8b6c4-102">How to Show and Hide Compiler Links</span></span>
<span data-ttu-id="8b6c4-103">在编译映射时，BizTalk 映射器将创建名为编译器链接以说明在映射中所需的所有链接的其他链接。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-103">When you compile a map, BizTalk Mapper creates additional links, known as compiler links to account for all linking needed in the map.</span></span> <span data-ttu-id="8b6c4-104">下面的链接的一些仅隐含你创建的链接。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-104">Some of these links are only implied by the links you created.</span></span> <span data-ttu-id="8b6c4-105">当编译，或测试映射，在 Visual Studio 输出窗口中的最后一行，可显示或隐藏在主窗口中的这些其他编译器链接。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-105">When you compile, or test, a map, the final line in the Visual Studio Output window allows you to show or hide these additional compiler links in the main window.</span></span> <span data-ttu-id="8b6c4-106">默认情况下，编译器链接显示为红色虚线。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-106">By default, the compiler links appear as red dashed lines.</span></span>  
  
### <a name="to-show-or-hide-compiler-links"></a><span data-ttu-id="8b6c4-107">若要显示或隐藏编译器链接</span><span class="sxs-lookup"><span data-stu-id="8b6c4-107">To show or hide compiler links</span></span>  
  
1. <span data-ttu-id="8b6c4-108">在解决方案资源管理器，右键单击你想要查看，并单击其编译器链接的映射**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-108">In Solution Explorer, right-click the map whose complier links you want to view, and then click **Test Map**.</span></span>  
  
2. <span data-ttu-id="8b6c4-109">在 Visual Studio 错误列表窗口中，滚动至末尾并双击显示的行**双击此处进行显示/隐藏编译器链接**。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-109">In the Visual Studio Error List window, scroll to the end and double-click the line that says **Double-click here to show/Hide compiler links**.</span></span>  
  
    <span data-ttu-id="8b6c4-110">为更改从编译器链接的显示状态向显示隐藏的或从隐藏到所示，只需双击试的行。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-110">To change the display state of compiler links from shown to hidden, or from hidden to shown, just double-click that line again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8b6c4-111">当你生成/重新生成 BizTalk 项目或解决方案，其中包含一个或多个映射，该消息**双击此处进行显示/隐藏编译器链接**中显示**错误列表**适用于 Visual Studio 窗口项目或解决方案中的所有映射。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-111">When you build/rebuild a BizTalk project or solution containing one or more maps, the message **Double-click here to show/Hide compiler links** is displayed in the **Error List** window of Visual Studio for all the maps in the project or solution.</span></span>  
  
   <span data-ttu-id="8b6c4-112">若要测试映射，必须配置为输入和输出实例属性。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-112">To test a map, you must configure the properties for the input and output instances.</span></span> <span data-ttu-id="8b6c4-113">有关如何配置这些属性的详细信息，请参阅[如何配置映射验证和测试参数](../core/how-to-configure-map-validation-and-test-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="8b6c4-113">For more information about how to configure these properties, see [How to Configure Map Validation and Test Parameters](../core/how-to-configure-map-validation-and-test-parameters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6c4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b6c4-114">See Also</span></span>  
 [<span data-ttu-id="8b6c4-115">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="8b6c4-115">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)