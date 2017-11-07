---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b669c06c5c474d5ce134b593dcecd110c6e8d572
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="a8d66-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="a8d66-101">Deployment Limitations</span></span>
<span data-ttu-id="a8d66-102">传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中，将导出由 BizTalk Server 中，并且它将传递给在同一个管理组件格式。</span><span class="sxs-lookup"><span data-stu-id="a8d66-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="a8d66-103">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="a8d66-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="a8d66-104">输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="a8d66-104">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="a8d66-105">这是一项已知的缺限。</span><span class="sxs-lookup"><span data-stu-id="a8d66-105">This is a known limitation.</span></span> <span data-ttu-id="a8d66-106">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="a8d66-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="a8d66-107">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="a8d66-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="a8d66-108">下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。</span><span class="sxs-lookup"><span data-stu-id="a8d66-108">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="a8d66-109">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="a8d66-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="a8d66-110">在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。</span><span class="sxs-lookup"><span data-stu-id="a8d66-110">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="a8d66-111">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="a8d66-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="a8d66-112">若要解决此密码限制问题，可使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="a8d66-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="a8d66-113">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="a8d66-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a8d66-114">出于安全考虑，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="a8d66-114">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="a8d66-115">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="a8d66-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="a8d66-116">输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="a8d66-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8d66-117">只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="a8d66-117">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="a8d66-118">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="a8d66-118">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
