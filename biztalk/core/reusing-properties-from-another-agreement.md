---
title: "重复使用来自另一个协议属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2a4e1efbfb7a86c18fb3643a789312a3707a72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reusing-properties-from-another-agreement"></a><span data-ttu-id="bea40-102">重用其他协议的属性</span><span class="sxs-lookup"><span data-stu-id="bea40-102">Reusing Properties from Another Agreement</span></span>
<span data-ttu-id="bea40-103">您可以重复使用协议之间的属性。</span><span class="sxs-lookup"><span data-stu-id="bea40-103">You can reuse properties between agreements.</span></span> <span data-ttu-id="bea40-104">当新协议的大多数或所有属性与现有协议的属性相同时，此操作可以节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="bea40-104">This can save a significant amount of time when either most or all of the properties of a new agreement are the same as those of an existing agreement.</span></span> <span data-ttu-id="bea40-105">通过 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] 中的 [!INCLUDE[prague](../includes/prague-md.md)] 用户界面，您可以将协议导出到 XML 模板文件。</span><span class="sxs-lookup"><span data-stu-id="bea40-105">The [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] user interface in [!INCLUDE[prague](../includes/prague-md.md)] enables you to export an agreement into an XML template file.</span></span> <span data-ttu-id="bea40-106">然后，您可以导入该 XML 模板以重复使用相同的协议属性。</span><span class="sxs-lookup"><span data-stu-id="bea40-106">You can then import the XML template to reuse the same agreement properties.</span></span>  
  
 <span data-ttu-id="bea40-107">导出协议到 XML 模板可捕获该协议的大多数属性，但并非全部。</span><span class="sxs-lookup"><span data-stu-id="bea40-107">Exporting the agreement to an XML template captures most, but not all, properties from the agreement.</span></span> <span data-ttu-id="bea40-108">以下属性将*不*导出到 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="bea40-108">The following properties will *not* be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="bea40-109">中的所有属性**常规属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bea40-109">All the properties from the **General Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bea40-110">中的所有属性**联系人**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bea40-110">All the properties from the **Contacts** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bea40-111">中的所有属性**其他属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bea40-111">All the properties from the **Additional Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bea40-112">从标识符相关设置**标识符**的单向协议选项卡中的页。这些是：</span><span class="sxs-lookup"><span data-stu-id="bea40-112">Identifier-related settings from the **Identifiers** page in the one-way agreement tab. These are:</span></span>  
  
    -   <span data-ttu-id="bea40-113">**对于 X12**: ISA5、 ISA6、 ISA7、 ISA8，和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="bea40-113">**For X12**: ISA5, ISA6, ISA7, ISA8, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="bea40-114">**对于 EDIFACT**: UNB 2.1、 UNB 2.2、 UNB 3.1、 UNB 3.2 和其他协议解析器设置</span><span class="sxs-lookup"><span data-stu-id="bea40-114">**For EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="bea40-115">**对于 AS2**: AS2-到 AS2-从，和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="bea40-115">**For AS2**: AS2-To, AS2-From, and additional agreement resolver settings</span></span>  
  
-   <span data-ttu-id="bea40-116">发送端口关联从**发送端口**页在单向协议选项卡中的 X12、 EDIFACT 和 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="bea40-116">Send port association from the **Send Ports** page in the one-way agreement tab for X12, EDIFACT, and AS2 agreements.</span></span>  
  
 <span data-ttu-id="bea40-117">除以上所列属性之外，以下属性将被导出至 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="bea40-117">Other than the properties listed above, the following properties will be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="bea40-118">所有与编码协议（X12、EDIFACT 或 AS2）相关的设置。</span><span class="sxs-lookup"><span data-stu-id="bea40-118">All settings related to the encoding protocol (X12, EDIFACT, or AS2).</span></span>  
  
-   <span data-ttu-id="bea40-119">所有与批相关的设置（批 ID 除外）。</span><span class="sxs-lookup"><span data-stu-id="bea40-119">All the batch-related settings (other than the batch ID).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bea40-120">在复制属性到目标协议时所有相应属性都将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="bea40-120">All the applicable properties will be overwritten when you copy properties to the destination agreement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bea40-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="bea40-121">In This Section</span></span>  
  
-   [<span data-ttu-id="bea40-122">导出到 XML 文件的协议属性</span><span class="sxs-lookup"><span data-stu-id="bea40-122">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [<span data-ttu-id="bea40-123">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="bea40-123">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="bea40-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bea40-124">See Also</span></span>  
 [<span data-ttu-id="bea40-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="bea40-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)