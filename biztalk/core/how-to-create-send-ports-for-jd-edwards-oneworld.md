---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e2101cee6e82283984bd0e830a583a96613d21b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385424"
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="1c7fd-101">如何创建 JD Edwards OneWorld 的发送端口</span><span class="sxs-lookup"><span data-stu-id="1c7fd-101">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="1c7fd-102">使用以下过程创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-102">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="1c7fd-103">若要创建的发送端口</span><span class="sxs-lookup"><span data-stu-id="1c7fd-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="1c7fd-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后导航到所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="1c7fd-105">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1c7fd-106">此外可以使用**静态单向端口**。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-106">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="1c7fd-107">在中**发送端口属性**对话框中**名称**字段中，键入发送端口名称 (例如，键入**SendToJDE**。)</span><span class="sxs-lookup"><span data-stu-id="1c7fd-107">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="1c7fd-108">在中**类型**下拉列表中，选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-108">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="1c7fd-109">在中**URI**下拉列表中，选择发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-109">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="1c7fd-110">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1c7fd-110">Click **OK**.</span></span>  
  
