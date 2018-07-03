---
title: 从 XML 文件导入协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cafd590f4f5936c1d12614e7a2021bc5427d49d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969142"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="66b9c-102">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="66b9c-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="66b9c-103">本部分介绍如何从 XML 模板文件中导入协议属性。</span><span class="sxs-lookup"><span data-stu-id="66b9c-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66b9c-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="66b9c-104">Prerequisites</span></span>  
 <span data-ttu-id="66b9c-105">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="66b9c-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="66b9c-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="66b9c-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="66b9c-107">你必须导出协议到 XML 模板文件，如中所述[导出到 XML 文件的协议属性](../core/exporting-agreement-properties-to-an-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="66b9c-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="66b9c-108">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="66b9c-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="66b9c-109">在 BizTalk Server 管理控制台中，单击**参与方**节点下的**BizTalk Server 管理**并**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="66b9c-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="66b9c-110">在中**参与方和业务配置文件**页上，创建一个协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="66b9c-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="66b9c-111">在中**协议属性**对话框中，单击**从模板加载**。</span><span class="sxs-lookup"><span data-stu-id="66b9c-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66b9c-112">**从模板加载**选择协议的协议后才启用按钮。</span><span class="sxs-lookup"><span data-stu-id="66b9c-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="66b9c-113">在指定标准时，您也在隐式声明您只能导入同一编码标准的协议。</span><span class="sxs-lookup"><span data-stu-id="66b9c-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="66b9c-114">在中**开放**对话框中，浏览到 XML 模板文件的位置，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="66b9c-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="66b9c-115">在中**创建模板**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="66b9c-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b9c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="66b9c-116">See Also</span></span>  
 <span data-ttu-id="66b9c-117">[重用其他协议的属性](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="66b9c-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="66b9c-118">将协议属性导出为 XML 文件</span><span class="sxs-lookup"><span data-stu-id="66b9c-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)