---
title: 导出到 XML 文件的协议属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136f09b5-3e8c-4455-bd84-66cd27de6a44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2091482bfda8110fc36dc0431b80093b715695
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004942"
---
# <a name="exporting-agreement-properties-to-an-xml-file"></a><span data-ttu-id="99039-102">导出到 XML 文件的协议属性</span><span class="sxs-lookup"><span data-stu-id="99039-102">Exporting Agreement Properties to an XML FIle</span></span>
<span data-ttu-id="99039-103">本部分介绍了如何将协议属性导出为 XML 模板文件。</span><span class="sxs-lookup"><span data-stu-id="99039-103">This section provides instructions on how to export agreement properties to an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99039-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="99039-104">Prerequisites</span></span>  
 <span data-ttu-id="99039-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="99039-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-export-agreement-properties-to-an-xml-file"></a><span data-ttu-id="99039-106">将协议属性导出为 XML 文件</span><span class="sxs-lookup"><span data-stu-id="99039-106">To export agreement properties to an XML file</span></span>  
  
1.  <span data-ttu-id="99039-107">在 BizTalk Server 管理控制台中，单击**方**节点下的**BizTalk Server 管理**和**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="99039-107">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="99039-108">在**方和业务配置文件**页上，单击一个参与方，然后选择具有你想要导出的设置从的协议的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="99039-108">In the **Parties and Business Profiles** page, click a party and then the business profile that has the agreement you want to export the settings from.</span></span>  
  
2.  <span data-ttu-id="99039-109">上**方和业务配置文件**页上，在**协议**部分中，右键单击你想要将导出从属性然后单击的协议**属性**。</span><span class="sxs-lookup"><span data-stu-id="99039-109">On the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement you want to export properties from and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="99039-110">在**协议属性**对话框中，单击**另存为模板**。</span><span class="sxs-lookup"><span data-stu-id="99039-110">In the **Agreement Properties** dialog box, click **Save As Template**.</span></span>  
  
4.  <span data-ttu-id="99039-111">在**另存为**对话框中，浏览到你想要导出的 XML 文件以另一个地址，为 XML 文件中，提供一个名称然后单击的位置**保存**。</span><span class="sxs-lookup"><span data-stu-id="99039-111">In the **Save As** dialog box, browse to the location where you want to export the XML file to, provide a name for the XML file, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="99039-112">在**创建模板**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99039-112">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99039-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99039-113">See Also</span></span>  
 <span data-ttu-id="99039-114">[重复使用来自另一个协议的属性](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="99039-114">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="99039-115">从 XML 文件导入协议属性</span><span class="sxs-lookup"><span data-stu-id="99039-115">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)