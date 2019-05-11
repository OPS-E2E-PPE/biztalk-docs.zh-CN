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
ms.openlocfilehash: 8b304af8fbc455a3a18b21774ebc9f1b25e55257
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395595"
---
# <a name="reusing-properties-from-another-agreement"></a><span data-ttu-id="496d7-102">重用其他协议的属性</span><span class="sxs-lookup"><span data-stu-id="496d7-102">Reusing Properties from Another Agreement</span></span>
<span data-ttu-id="496d7-103">可以重复使用协议之间的属性。</span><span class="sxs-lookup"><span data-stu-id="496d7-103">You can reuse properties between agreements.</span></span> <span data-ttu-id="496d7-104">这样可以节省大量的时间时大多数或所有新协议的属性将与这些现有的协议相同。</span><span class="sxs-lookup"><span data-stu-id="496d7-104">This can save a significant amount of time when either most or all of the properties of a new agreement are the same as those of an existing agreement.</span></span> <span data-ttu-id="496d7-105">[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server 中的用户界面，可导出到 XML 模板文件的协议。</span><span class="sxs-lookup"><span data-stu-id="496d7-105">The [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] user interface in BizTalk Server enables you to export an agreement into an XML template file.</span></span> <span data-ttu-id="496d7-106">然后可以导入该 XML 模板以重复使用相同的协议属性。</span><span class="sxs-lookup"><span data-stu-id="496d7-106">You can then import the XML template to reuse the same agreement properties.</span></span>  
  
 <span data-ttu-id="496d7-107">导出协议到 XML 模板捕获最，而不是全部，协议的属性。</span><span class="sxs-lookup"><span data-stu-id="496d7-107">Exporting the agreement to an XML template captures most, but not all, properties from the agreement.</span></span> <span data-ttu-id="496d7-108">以下属性将*不*导出到 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="496d7-108">The following properties will *not* be exported to the XML template file:</span></span>  
  
- <span data-ttu-id="496d7-109">中的所有属性**常规属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="496d7-109">All the properties from the **General Properties** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="496d7-110">中的所有属性**联系人**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="496d7-110">All the properties from the **Contacts** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="496d7-111">中的所有属性**附加属性**页面**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="496d7-111">All the properties from the **Additional Properties** page in the **General** tab.</span></span>  
  
- <span data-ttu-id="496d7-112">从与标识符相关的设置**标识符**页的单向协议选项卡。这些是：</span><span class="sxs-lookup"><span data-stu-id="496d7-112">Identifier-related settings from the **Identifiers** page in the one-way agreement tab. These are:</span></span>  
  
  -   <span data-ttu-id="496d7-113">**对于 X12**:ISA5、 ISA6、 ISA7、 ISA8 和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="496d7-113">**For X12**: ISA5, ISA6, ISA7, ISA8, and additional agreement resolver settings</span></span>  
  
  -   <span data-ttu-id="496d7-114">**对于 EDIFACT**:UNB 2.1、 UNB 2.2、 UNB 3.1，UNB 3.2 和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="496d7-114">**For EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2, and additional agreement resolver settings</span></span>  
  
  -   <span data-ttu-id="496d7-115">**适用于 AS2**:AS2-To、as2-From、 和其他协议解析程序设置</span><span class="sxs-lookup"><span data-stu-id="496d7-115">**For AS2**: AS2-To, AS2-From, and additional agreement resolver settings</span></span>  
  
- <span data-ttu-id="496d7-116">发送端口关联**发送端口**协议中适用于 X12 和 AS2 的单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="496d7-116">Send port association from the **Send Ports** page in the one-way agreement tab for X12, EDIFACT, and AS2 agreements.</span></span>  
  
  <span data-ttu-id="496d7-117">上面列出的属性，以外的下列属性将导出到 XML 模板文件：</span><span class="sxs-lookup"><span data-stu-id="496d7-117">Other than the properties listed above, the following properties will be exported to the XML template file:</span></span>  
  
- <span data-ttu-id="496d7-118">所有与编码协议 (X12、 EDIFACT 或 AS2) 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="496d7-118">All settings related to the encoding protocol (X12, EDIFACT, or AS2).</span></span>  
  
- <span data-ttu-id="496d7-119">所有与批处理相关的设置 （而不是批处理 ID)。</span><span class="sxs-lookup"><span data-stu-id="496d7-119">All the batch-related settings (other than the batch ID).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="496d7-120">将属性复制到目标协议时，将覆盖所有适用的属性。</span><span class="sxs-lookup"><span data-stu-id="496d7-120">All the applicable properties will be overwritten when you copy properties to the destination agreement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="496d7-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="496d7-121">In This Section</span></span>  
  
-   [<span data-ttu-id="496d7-122">将协议属性导出为 XML 文件</span><span class="sxs-lookup"><span data-stu-id="496d7-122">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [<span data-ttu-id="496d7-123">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="496d7-123">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="496d7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="496d7-124">See Also</span></span>  
 [<span data-ttu-id="496d7-125">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="496d7-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)