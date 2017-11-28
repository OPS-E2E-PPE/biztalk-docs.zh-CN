---
title: "从 XML 文件导入协议属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3ac08628931ec4111eb1b5a9ad86991344c22d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="88db9-102">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="88db9-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="88db9-103">本部分介绍如何从 XML 模板文件中导入协议属性。</span><span class="sxs-lookup"><span data-stu-id="88db9-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="88db9-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="88db9-104">Prerequisites</span></span>  
 <span data-ttu-id="88db9-105">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="88db9-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="88db9-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="88db9-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="88db9-107">你必须导出协议到 XML 模板文件，如中所述[导出到 XML 文件的协议属性](../core/exporting-agreement-properties-to-an-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="88db9-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="88db9-108">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="88db9-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="88db9-109">在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理控制台中，单击**方**节点下的**BizTalk Server 管理**和**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="88db9-109">In the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="88db9-110">在**方和业务配置文件**页上，创建了协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="88db9-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="88db9-111">在**协议属性**对话框中，单击**负载从模板**。</span><span class="sxs-lookup"><span data-stu-id="88db9-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88db9-112">**负载从模板**仅在选择一种协议的协议后，才启用按钮。</span><span class="sxs-lookup"><span data-stu-id="88db9-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="88db9-113">在指定标准时，您也在隐式声明您只能导入同一编码标准的协议。</span><span class="sxs-lookup"><span data-stu-id="88db9-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="88db9-114">在**打开**对话框中，浏览到的 XML 模板文件的位置，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="88db9-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="88db9-115">在**创建模板**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="88db9-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88db9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88db9-116">See Also</span></span>  
 <span data-ttu-id="88db9-117">[重复使用来自另一个协议的属性](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="88db9-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="88db9-118">导出到 XML 文件的协议属性</span><span class="sxs-lookup"><span data-stu-id="88db9-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)