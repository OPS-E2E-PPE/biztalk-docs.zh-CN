---
title: 保留在平面文件汇编管道组件的分隔符 |Microsoft 文档
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
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268781"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="6ef49-102">保留平面文件组装器管道组件中的分隔符</span><span class="sxs-lookup"><span data-stu-id="6ef49-102">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="6ef49-103">如果在经过使用平面文件组装器的自定义管道的消息中缺少某些记录，则根据输入文件中缺少记录的位置，这些记录的分隔符不一定出现在平面文件输出中。</span><span class="sxs-lookup"><span data-stu-id="6ef49-103">If there are missing records in the message going through a custom pipeline that uses the Flat File Assembler, the delimiter for those records may or may not appear in the flat file output depending on where in the input file the records are missing.</span></span>  
  
 <span data-ttu-id="6ef49-104">若要确保该平面文件保留某些分隔符，您可以使用映射和自定义脚本，确保在特定输入记录在消息中不存在时创建一条“空”记录。</span><span class="sxs-lookup"><span data-stu-id="6ef49-104">To ensure that the flat file retain certain delimiters, you can use a map and a custom script to make sure an "empty" record is created when a specific input record does not exist in the message.</span></span> <span data-ttu-id="6ef49-105">为此，您必须确保平面文件组装器的文档架构中可能的空节点设置了如下属性：</span><span class="sxs-lookup"><span data-stu-id="6ef49-105">For this to work, you must make sure that the potentially empty nodes in the document schema for the Flat File Assembler have the following properties set as shown:</span></span>  
  
|<span data-ttu-id="6ef49-106">属性</span><span class="sxs-lookup"><span data-stu-id="6ef49-106">Property</span></span>|<span data-ttu-id="6ef49-107">设置</span><span class="sxs-lookup"><span data-stu-id="6ef49-107">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="6ef49-108">为空数据保留分隔符</span><span class="sxs-lookup"><span data-stu-id="6ef49-108">Preserve Delimiter for Empty Data</span></span>|<span data-ttu-id="6ef49-109">是</span><span class="sxs-lookup"><span data-stu-id="6ef49-109">Yes</span></span>|  
|<span data-ttu-id="6ef49-110">禁止显示尾随分隔符</span><span class="sxs-lookup"><span data-stu-id="6ef49-110">Suppress Trailing Delimiters</span></span>|<span data-ttu-id="6ef49-111">是</span><span class="sxs-lookup"><span data-stu-id="6ef49-111">No</span></span>|  
|<span data-ttu-id="6ef49-112">生成空节点（对根节点进行这一设置）</span><span class="sxs-lookup"><span data-stu-id="6ef49-112">Generate Empty Nodes (set this on the root node)</span></span>|<span data-ttu-id="6ef49-113">True</span><span class="sxs-lookup"><span data-stu-id="6ef49-113">True</span></span>|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a><span data-ttu-id="6ef49-114">创建将创建“空”记录的映射</span><span class="sxs-lookup"><span data-stu-id="6ef49-114">To create a map that creates an "empty" record</span></span>  
  
1.  <span data-ttu-id="6ef49-115">向 BizTalk 项目添加新映射。</span><span class="sxs-lookup"><span data-stu-id="6ef49-115">Add a new map to your BizTalk project.</span></span>  
  
2.  <span data-ttu-id="6ef49-116">将平面文件组装器使用的文档架构指定为映射源和映射目标架构。</span><span class="sxs-lookup"><span data-stu-id="6ef49-116">Specify the document schema used by the Flat File Assembler as both the map source and map destination schema.</span></span>  
  
3.  <span data-ttu-id="6ef49-117">将不为空的源字段映射到相应的目标字段。</span><span class="sxs-lookup"><span data-stu-id="6ef49-117">Map the source fields that will not be empty to the corresponding destination fields.</span></span>  
  
4.  <span data-ttu-id="6ef49-118">对于可能为空的那些字段，使用自定义脚本来检查源字段是否为空并返回空字符串（而非 Nil）。</span><span class="sxs-lookup"><span data-stu-id="6ef49-118">For those fields that may be empty, use a custom script to check if the source field is empty and return an empty string (instead of Nil).</span></span> <span data-ttu-id="6ef49-119">使用如下脚本：</span><span class="sxs-lookup"><span data-stu-id="6ef49-119">Use a script like the following:</span></span>  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6ef49-120">您必须创建对于您映射的每个可能的空字段都具有唯一函数名的脚本。</span><span class="sxs-lookup"><span data-stu-id="6ef49-120">You must create a script with a unique function name for each potentially empty field you map.</span></span> <span data-ttu-id="6ef49-121">例如，如果你有可能为空的三个字段，你可能有函数名为`ValOrEmpty1`， `ValOrEmpty2`， `ValOrEmpty3`。</span><span class="sxs-lookup"><span data-stu-id="6ef49-121">For example, if you have three fields that may be empty, you might have functions named `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span></span>  
  
5.  <span data-ttu-id="6ef49-122">使用 BizTalk Server 管理控制台，将配置发送端口的自定义管道和平面文件汇编组件以使用为出站映射的映射。</span><span class="sxs-lookup"><span data-stu-id="6ef49-122">Using BizTalk Server Administration console, configure the send port with the custom pipeline and flat file assembler component to use the map as an outbound map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef49-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ef49-123">See Also</span></span>  
 <span data-ttu-id="6ef49-124">[如何配置为发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="6ef49-124">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="6ef49-125">平面文件汇编管道组件</span><span class="sxs-lookup"><span data-stu-id="6ef49-125">Flat File Assembler Pipeline Component</span></span>](../core/flat-file-assembler-pipeline-component.md)