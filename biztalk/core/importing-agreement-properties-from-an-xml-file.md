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
ms.openlocfilehash: 13b8189ce340cb541ab0535f40312f9deec90796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382559"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="8c54e-102">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="8c54e-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="8c54e-103">本部分将说明了如何从 XML 模板文件中导入协议属性。</span><span class="sxs-lookup"><span data-stu-id="8c54e-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c54e-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="8c54e-104">Prerequisites</span></span>  
 <span data-ttu-id="8c54e-105">在本主题中执行该过程的先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="8c54e-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="8c54e-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="8c54e-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="8c54e-107">你必须导出协议到 XML 模板文件，如中所述[导出到 XML 文件的协议属性](../core/exporting-agreement-properties-to-an-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="8c54e-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="8c54e-108">若要从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="8c54e-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="8c54e-109">在 BizTalk Server 管理控制台中，单击**参与方**节点下的**BizTalk Server 管理**并**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="8c54e-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="8c54e-110">在中**参与方和业务配置文件**页上，创建一个协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="8c54e-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="8c54e-111">在中**协议属性**对话框中，单击**从模板加载**。</span><span class="sxs-lookup"><span data-stu-id="8c54e-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8c54e-112">**从模板加载**选择协议的协议后才启用按钮。</span><span class="sxs-lookup"><span data-stu-id="8c54e-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="8c54e-113">在指定协议时你还将隐式声明，可以只导入相同的编码协议的协议。</span><span class="sxs-lookup"><span data-stu-id="8c54e-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="8c54e-114">在中**开放**对话框中，浏览到 XML 模板文件的位置，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="8c54e-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="8c54e-115">在中**创建模板**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c54e-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c54e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c54e-116">See Also</span></span>  
 <span data-ttu-id="8c54e-117">[重用其他协议的属性](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="8c54e-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="8c54e-118">将协议属性导出为 XML 文件</span><span class="sxs-lookup"><span data-stu-id="8c54e-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)