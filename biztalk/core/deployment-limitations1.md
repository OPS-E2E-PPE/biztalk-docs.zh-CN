---
title: "部署 Limitations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="bc8b7-102">部署限制</span><span class="sxs-lookup"><span data-stu-id="bc8b7-102">Deployment Limitations</span></span>
<span data-ttu-id="bc8b7-103">传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中，将导出由 BizTalk Server 中，并且它将传递给在同一个管理组件格式。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-103">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="bc8b7-104">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="bc8b7-105">输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-105">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="bc8b7-106">这是一项已知的缺限。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-106">This is a known limitation.</span></span> <span data-ttu-id="bc8b7-107">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-107">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="bc8b7-108">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-108">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="bc8b7-109">下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-109">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="bc8b7-110">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-110">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="bc8b7-111">在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-111">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc8b7-112">导入中的.msi 文件时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含的任何企业适配器的绑定信息的应用程序可能会收到一条导入错误消息。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-112">When importing an .msi file in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="bc8b7-113">受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-113">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="bc8b7-114">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="bc8b7-114">Password Limitation Workaround</span></span>  
 <span data-ttu-id="bc8b7-115">若要解决此密码限制问题，可使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="bc8b7-115">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="bc8b7-116">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bc8b7-117">出于安全考虑，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-117">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="bc8b7-118">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="bc8b7-119">输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-119">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc8b7-120">只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-120">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="bc8b7-121">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="bc8b7-121">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8b7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc8b7-122">See Also</span></span>  
 [<span data-ttu-id="bc8b7-123">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="bc8b7-123">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)