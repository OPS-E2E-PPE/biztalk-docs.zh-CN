---
title: "部署 Limitations4 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, limitations
ms.assetid: 1312627e-9de2-461e-a8c4-66a9d41bb714
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d8e33c7274ab0f95c6d7fff1bf9746ac86e420
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="bb92d-102">部署限制</span><span class="sxs-lookup"><span data-stu-id="bb92d-102">Deployment Limitations</span></span>
<span data-ttu-id="bb92d-103">传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="bb92d-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="bb92d-104">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="bb92d-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="bb92d-105">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="bb92d-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="bb92d-106">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="bb92d-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="bb92d-107">下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="bb92d-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="bb92d-108">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="bb92d-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="bb92d-109">在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。</span><span class="sxs-lookup"><span data-stu-id="bb92d-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb92d-110">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中导入包含针对任何企业适配器的绑定信息的 .msi 文件时，可能会收到一条导入错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb92d-110">When importing an .msi file in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="bb92d-111">受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087)。</span><span class="sxs-lookup"><span data-stu-id="bb92d-111">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="bb92d-112">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="bb92d-112">Password Limitation Workaround</span></span>  
 <span data-ttu-id="bb92d-113">若要解决此密码限制问题，您可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="bb92d-113">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="bb92d-114">若要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="bb92d-114">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="bb92d-115">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="bb92d-115">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="bb92d-116">使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="bb92d-116">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="bb92d-117">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="bb92d-117">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb92d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb92d-118">See Also</span></span>  
 [<span data-ttu-id="bb92d-119">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="bb92d-119">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)