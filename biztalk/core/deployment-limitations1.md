---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 44fa3a4b614e70b424b8d3b18d058cd8817cc705
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351846"
---
# <a name="deployment-limitations"></a><span data-ttu-id="d5703-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="d5703-101">Deployment Limitations</span></span>
<span data-ttu-id="d5703-102">传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中的已导出的 BizTalk Server 中，并且传递至中相同的管理组件格式。</span><span class="sxs-lookup"><span data-stu-id="d5703-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="d5703-103">星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d5703-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="d5703-104">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="d5703-104">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="d5703-105">这是已知的限制。</span><span class="sxs-lookup"><span data-stu-id="d5703-105">This is a known limitation.</span></span> <span data-ttu-id="d5703-106">在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。</span><span class="sxs-lookup"><span data-stu-id="d5703-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="d5703-107">这可以防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="d5703-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="d5703-108">下一次使用该文件导入绑定信息时，您必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="d5703-108">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="d5703-109">或者，暂时可以通过将密码输入到其导入前修改绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d5703-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="d5703-110">在这种情况下，必须从绑定文件删除密码，在导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="d5703-110">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="d5703-111">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="d5703-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="d5703-112">若要解决此密码限制，可以使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="d5703-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="d5703-113">星号替换为纯文本导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d5703-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d5703-114">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="d5703-114">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="d5703-115">星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d5703-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="d5703-116">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="d5703-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5703-117">这种解决可仅当目标计算机上安装 Visual Studio 或者您开发一个自定义工具。</span><span class="sxs-lookup"><span data-stu-id="d5703-117">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="d5703-118">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="d5703-118">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
