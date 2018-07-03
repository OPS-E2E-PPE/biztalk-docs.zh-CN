---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9d12874ef6042580183f407afc811a9d7f6e0fc9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009862"
---
# <a name="deployment-limitations"></a><span data-ttu-id="15c9c-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="15c9c-101">Deployment Limitations</span></span>

## <a name="overview"></a><span data-ttu-id="15c9c-102">概述</span><span class="sxs-lookup"><span data-stu-id="15c9c-102">Overview</span></span>
<span data-ttu-id="15c9c-103">传输适配器密码在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出的绑定文件中以星号 (******) 的形式进行存储，并且以同样的格式传递至管理组件。</span><span class="sxs-lookup"><span data-stu-id="15c9c-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="15c9c-104">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="15c9c-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="15c9c-105">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="15c9c-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="15c9c-106">下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。</span><span class="sxs-lookup"><span data-stu-id="15c9c-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="15c9c-107">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="15c9c-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="15c9c-108">在这种情况下，必须在完成导入操作后从绑定文件中删除密码。</span><span class="sxs-lookup"><span data-stu-id="15c9c-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="15c9c-109">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="15c9c-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="15c9c-110">若要解决此密码限制问题，可使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="15c9c-110">To work around this password limitation, you can use one of the following methods:</span></span>  
  
- <span data-ttu-id="15c9c-111">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="15c9c-111">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
  > [!CAUTION]
  >  <span data-ttu-id="15c9c-112">出于安全考虑，不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="15c9c-112">This practice is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="15c9c-113">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="15c9c-113">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="15c9c-114">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="15c9c-114">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="15c9c-115">只有当目标计算机上安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 或者您开发了一个自定义工具时，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="15c9c-115">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
  <span data-ttu-id="15c9c-116">-或-</span><span class="sxs-lookup"><span data-stu-id="15c9c-116">-or-</span></span>  
  
- <span data-ttu-id="15c9c-117">使用企业单一登录 (SSO) 而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="15c9c-117">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
   <span data-ttu-id="15c9c-118">使用 SSO 选项时需要导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="15c9c-118">Using the SSO option requires an import of the binding file.</span></span>  
  
  <span data-ttu-id="15c9c-119">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="15c9c-119">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c9c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="15c9c-120">See Also</span></span>  
[<span data-ttu-id="15c9c-121">导入绑定和限制</span><span class="sxs-lookup"><span data-stu-id="15c9c-121">Import bindings & limitations</span></span>](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)