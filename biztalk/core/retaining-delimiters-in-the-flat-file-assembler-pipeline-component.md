---
title: 保留平面文件组装器管道组件中的分隔符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f975f04bb18dca5cc8e311fdb21d7b44caf01d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322134"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="9bc7d-102">保留平面文件组装器管道组件中的分隔符</span><span class="sxs-lookup"><span data-stu-id="9bc7d-102">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="9bc7d-103">如果消息经过使用平面文件组装器的自定义管道中有缺失的记录，这些记录的分隔符可能或可能不会显示在平面文件输出，具体取决于在其中输入文件中的记录将会丢失。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-103">If there are missing records in the message going through a custom pipeline that uses the Flat File Assembler, the delimiter for those records may or may not appear in the flat file output depending on where in the input file the records are missing.</span></span>  
  
 <span data-ttu-id="9bc7d-104">以确保该平面文件保留某些分隔符，则可以使用映射和自定义脚本以确保在特定输入的记录不存在消息中时，将创建"空"记录。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-104">To ensure that the flat file retain certain delimiters, you can use a map and a custom script to make sure an "empty" record is created when a specific input record does not exist in the message.</span></span> <span data-ttu-id="9bc7d-105">为实现此目的，你必须确保平面文件组装器的文档架构中的可能的空节点已按所示设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9bc7d-105">For this to work, you must make sure that the potentially empty nodes in the document schema for the Flat File Assembler have the following properties set as shown:</span></span>  
  
|<span data-ttu-id="9bc7d-106">属性</span><span class="sxs-lookup"><span data-stu-id="9bc7d-106">Property</span></span>|<span data-ttu-id="9bc7d-107">设置</span><span class="sxs-lookup"><span data-stu-id="9bc7d-107">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="9bc7d-108">为空数据保留分隔符</span><span class="sxs-lookup"><span data-stu-id="9bc7d-108">Preserve Delimiter for Empty Data</span></span>|<span data-ttu-id="9bc7d-109">是</span><span class="sxs-lookup"><span data-stu-id="9bc7d-109">Yes</span></span>|  
|<span data-ttu-id="9bc7d-110">取消尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="9bc7d-110">Suppress Trailing Delimiters</span></span>|<span data-ttu-id="9bc7d-111">否</span><span class="sxs-lookup"><span data-stu-id="9bc7d-111">No</span></span>|  
|<span data-ttu-id="9bc7d-112">生成空节点 （这在设置的根节点）</span><span class="sxs-lookup"><span data-stu-id="9bc7d-112">Generate Empty Nodes (set this on the root node)</span></span>|<span data-ttu-id="9bc7d-113">True</span><span class="sxs-lookup"><span data-stu-id="9bc7d-113">True</span></span>|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a><span data-ttu-id="9bc7d-114">若要创建映射，将创建一个"空"记录</span><span class="sxs-lookup"><span data-stu-id="9bc7d-114">To create a map that creates an "empty" record</span></span>  
  
1.  <span data-ttu-id="9bc7d-115">向 BizTalk 项目添加新的映射。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-115">Add a new map to your BizTalk project.</span></span>  
  
2.  <span data-ttu-id="9bc7d-116">指定使用平面文件组装器作为映射源和映射目标架构的文档架构。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-116">Specify the document schema used by the Flat File Assembler as both the map source and map destination schema.</span></span>  
  
3.  <span data-ttu-id="9bc7d-117">将不为空到相应的目标字段的源字段映射。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-117">Map the source fields that will not be empty to the corresponding destination fields.</span></span>  
  
4.  <span data-ttu-id="9bc7d-118">这些字段可能为空的使用自定义脚本来检查源字段是否为空并返回空字符串 （而非 Nil)。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-118">For those fields that may be empty, use a custom script to check if the source field is empty and return an empty string (instead of Nil).</span></span> <span data-ttu-id="9bc7d-119">使用脚本如下所示：</span><span class="sxs-lookup"><span data-stu-id="9bc7d-119">Use a script like the following:</span></span>  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9bc7d-120">替换为您映射的每个可能的空字段的唯一函数名称，必须创建一个脚本。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-120">You must create a script with a unique function name for each potentially empty field you map.</span></span> <span data-ttu-id="9bc7d-121">例如，如果有三个字段可能为空的则可能必须名为的函数`ValOrEmpty1`， `ValOrEmpty2`， `ValOrEmpty3`。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-121">For example, if you have three fields that may be empty, you might have functions named `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span></span>  
  
5.  <span data-ttu-id="9bc7d-122">使用 BizTalk Server 管理控制台中，使用自定义管道和平面文件组装器组件以将映射用作出站映射配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="9bc7d-122">Using BizTalk Server Administration console, configure the send port with the custom pipeline and flat file assembler component to use the map as an outbound map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc7d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bc7d-123">See Also</span></span>  
 <span data-ttu-id="9bc7d-124">[如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="9bc7d-124">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="9bc7d-125">平面文件汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="9bc7d-125">Flat File Assembler Pipeline Component</span></span>](../core/flat-file-assembler-pipeline-component.md)