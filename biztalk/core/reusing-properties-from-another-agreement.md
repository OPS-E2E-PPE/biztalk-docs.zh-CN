---
title: 重用其他协议的属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7f2799f21e16d1622f180229d14cb8bb93d4a67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021193"
---
# <a name="reusing-properties-from-another-agreement"></a><span data-ttu-id="88048-102">重用其他协议的属性</span><span class="sxs-lookup"><span data-stu-id="88048-102">Reusing Properties from Another Agreement</span></span>
<span data-ttu-id="88048-103">您可以重复使用协议之间的属性。</span><span class="sxs-lookup"><span data-stu-id="88048-103">You can reuse properties between agreements.</span></span> <span data-ttu-id="88048-104">当新协议的大多数或所有属性与现有协议的属性相同时，此操作可以节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="88048-104">This can save a significant amount of time when either most or all of the properties of a new agreement are the same as those of an existing agreement.</span></span> <span data-ttu-id="88048-105">[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server 中的用户界面，可导出到 XML 模板文件的协议。</span><span class="sxs-lookup"><span data-stu-id="88048-105">The [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] user interface in BizTalk Server enables you to export an agreement into an XML template file.</span></span> <span data-ttu-id="88048-106">然后，您可以导入该 XML 模板以重复使用相同的协议属性。</span><span class="sxs-lookup"><span data-stu-id="88048-106">You can then import the XML template to reuse the same agreement properties.</span></span>  
  
 <span data-ttu-id="88048-107">导出协议到 XML 模板可捕获该协议的大多数属性，但并非全部。</span><span class="sxs-lookup"><span data-stu-id="88048-107">Exporting the agreement to an XML template captures most, but not all, properties from the agreement.</span></span> <span data-ttu-id="88048-108">以下属性将*不*导出到 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="88048-108">The following properties will *not* be exported to the XML template file:</span></span>  
  
- <span data-ttu-id="88048-109">中的所有属性**常规属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="88048-109">All the properties from the **General Properties** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="88048-110">中的所有属性**联系人**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="88048-110">All the properties from the **Contacts** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="88048-111">中的所有属性**附加属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="88048-111">All the properties from the **Additional Properties** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="88048-112">从与标识符相关的设置**标识符**页的单向协议选项卡。以下是：</span><span class="sxs-lookup"><span data-stu-id="88048-112">Identifier-related settings from the **Identifiers** page in the one-way agreement tab. These are:</span></span>  
  
  -   <span data-ttu-id="88048-113">**对于 X12**: ISA5、 ISA6、 ISA7、 ISA8，和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="88048-113">**For X12**: ISA5, ISA6, ISA7, ISA8, and additional agreement resolver settings</span></span>  
  
  -   <span data-ttu-id="88048-114">**对于 EDIFACT**: UNB 2.1、 UNB 2.2、 UNB 3.1，UNB 3.2 和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="88048-114">**For EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2, and additional agreement resolver settings</span></span>  
  
  -   <span data-ttu-id="88048-115">**适用于 AS2**: AS2-To、as2-From、 和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="88048-115">**For AS2**: AS2-To, AS2-From, and additional agreement resolver settings</span></span>  
  
- <span data-ttu-id="88048-116">发送端口关联**发送端口**协议中适用于 X12 和 AS2 的单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="88048-116">Send port association from the **Send Ports** page in the one-way agreement tab for X12, EDIFACT, and AS2 agreements.</span></span>  
  
  <span data-ttu-id="88048-117">除以上所列属性之外，以下属性将被导出至 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="88048-117">Other than the properties listed above, the following properties will be exported to the XML template file:</span></span>  
  
- <span data-ttu-id="88048-118">所有与编码协议（X12、EDIFACT 或 AS2）相关的设置。</span><span class="sxs-lookup"><span data-stu-id="88048-118">All settings related to the encoding protocol (X12, EDIFACT, or AS2).</span></span>  
  
- <span data-ttu-id="88048-119">所有与批相关的设置（批 ID 除外）。</span><span class="sxs-lookup"><span data-stu-id="88048-119">All the batch-related settings (other than the batch ID).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88048-120">在复制属性到目标协议时所有相应属性都将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="88048-120">All the applicable properties will be overwritten when you copy properties to the destination agreement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88048-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="88048-121">In This Section</span></span>  
  
-   [<span data-ttu-id="88048-122">将协议属性导出为 XML 文件</span><span class="sxs-lookup"><span data-stu-id="88048-122">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [<span data-ttu-id="88048-123">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="88048-123">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="88048-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="88048-124">See Also</span></span>  
 [<span data-ttu-id="88048-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="88048-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)