---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9fa12a82defc21cf0094cad7164ddd096442d87e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351839"
---
# <a name="deployment-limitations"></a><span data-ttu-id="824e7-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="824e7-101">Deployment Limitations</span></span>

## <a name="overview"></a><span data-ttu-id="824e7-102">概述</span><span class="sxs-lookup"><span data-stu-id="824e7-102">Overview</span></span>
<span data-ttu-id="824e7-103">传输适配器密码在导出的绑定文件中存储为星号 （\*） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="824e7-103">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="824e7-104">在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。</span><span class="sxs-lookup"><span data-stu-id="824e7-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="824e7-105">这可以防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="824e7-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="824e7-106">下一次使用该文件导入绑定信息时，您必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="824e7-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="824e7-107">或者，暂时可以通过将密码输入到其导入前修改绑定文件。</span><span class="sxs-lookup"><span data-stu-id="824e7-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="824e7-108">在这种情况下，必须从绑定文件删除密码，在导入操作完成后。</span><span class="sxs-lookup"><span data-stu-id="824e7-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="824e7-109">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="824e7-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="824e7-110">若要解决此密码限制，可以使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="824e7-110">To work around this password limitation, you can use one of the following methods:</span></span>  
  
- <span data-ttu-id="824e7-111">星号替换为纯文本导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="824e7-111">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
  > [!CAUTION]
  >  <span data-ttu-id="824e7-112">出于安全原因不推荐此操作。</span><span class="sxs-lookup"><span data-stu-id="824e7-112">This practice is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="824e7-113">星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="824e7-113">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="824e7-114">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="824e7-114">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="824e7-115">这种解决可以仅当使用 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装在目标计算机上或者您开发一个自定义工具。</span><span class="sxs-lookup"><span data-stu-id="824e7-115">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
  <span data-ttu-id="824e7-116">-或-</span><span class="sxs-lookup"><span data-stu-id="824e7-116">-or-</span></span>  
  
- <span data-ttu-id="824e7-117">使用企业单一登录 (SSO) 而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="824e7-117">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
   <span data-ttu-id="824e7-118">使用 SSO 选项，需要导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="824e7-118">Using the SSO option requires an import of the binding file.</span></span>  
  
  <span data-ttu-id="824e7-119">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="824e7-119">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824e7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="824e7-120">See Also</span></span>  
[<span data-ttu-id="824e7-121">导入绑定和限制</span><span class="sxs-lookup"><span data-stu-id="824e7-121">Import bindings & limitations</span></span>](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)