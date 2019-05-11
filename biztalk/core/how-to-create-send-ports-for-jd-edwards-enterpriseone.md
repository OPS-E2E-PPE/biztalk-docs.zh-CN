---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c6b672b57f9498c8270a1ee310d498cca6c0b3de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339005"
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="f80d1-101">如何创建 JD Edwards EnterpriseOne 的发送端口</span><span class="sxs-lookup"><span data-stu-id="f80d1-101">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="f80d1-102">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="f80d1-102">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="f80d1-103">若要创建的发送端口</span><span class="sxs-lookup"><span data-stu-id="f80d1-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="f80d1-104">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f80d1-104">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f80d1-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开要为其创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f80d1-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="f80d1-106">右键单击**发送端口**然后单击**新建**，然后单击**静态要求响应端口**。</span><span class="sxs-lookup"><span data-stu-id="f80d1-106">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="f80d1-107">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f80d1-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="f80d1-108">在中**名称**框中，键入发送端口名称 (例如， `SendToJDE`)。</span><span class="sxs-lookup"><span data-stu-id="f80d1-108">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="f80d1-109">从**类型**下拉列表中，选择**JDEdwards**。</span><span class="sxs-lookup"><span data-stu-id="f80d1-109">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="f80d1-110">从**发送处理程序**下拉列表中，选择发送处理程序地址。</span><span class="sxs-lookup"><span data-stu-id="f80d1-110">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="f80d1-111">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f80d1-111">Click **OK**.</span></span>  
  
