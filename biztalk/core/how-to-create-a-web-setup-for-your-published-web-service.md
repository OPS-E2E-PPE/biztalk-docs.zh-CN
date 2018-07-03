---
title: 如何为已发布的 Web 服务创建 Web 安装程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d894cba37b85c4f18fe2a05af33eb2f4e6e1981e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984382"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a><span data-ttu-id="8a351-102">如何为已发布的 Web Services 创建 Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="8a351-102">How to Create a Web Setup for Your Published Web Service</span></span>
<span data-ttu-id="8a351-103">可以创建一个安装包，以便于在生产环境中设置 Web Services。</span><span class="sxs-lookup"><span data-stu-id="8a351-103">You can create an installation package to facilitate setting up your Web service in a production environment.</span></span> <span data-ttu-id="8a351-104">这会生成一个 .MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="8a351-104">This produces an .MSI file.</span></span>  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a><span data-ttu-id="8a351-105">创建一个安装包以便使用 Visual Studio 生成 .MSI 文件</span><span class="sxs-lookup"><span data-stu-id="8a351-105">To create an installation package to produce an .MSI file using Visual Studio</span></span>  
  
1. <span data-ttu-id="8a351-106">打开已发布的 ASP.NET Web Services 项目。</span><span class="sxs-lookup"><span data-stu-id="8a351-106">Open your published ASP.NET Web service project.</span></span>  
  
2. <span data-ttu-id="8a351-107">在解决方案资源管理器，右键单击解决方案节点，单击**外**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="8a351-107">In Solution Explorer, right-click the solution node, click **Add**, and then click **New Project**.</span></span>  
  
3. <span data-ttu-id="8a351-108">在中**添加新项目**对话框中**项目类型**区域中，展开**其他项目类型**，展开**安装和部署项目**，然后选择**Visual Studio 安装程序**。</span><span class="sxs-lookup"><span data-stu-id="8a351-108">In the **Add New Project** dialog box, in the **Project Types** area, expand **Other Project Types**, expand **Setup and Deployment Projects**, and then select **Visual Studio Installer**.</span></span> <span data-ttu-id="8a351-109">在中**模板**区域中，选择**Web 安装项目**。</span><span class="sxs-lookup"><span data-stu-id="8a351-109">In the **Templates** area, select **Web Setup Project**.</span></span>  
  
4. <span data-ttu-id="8a351-110">在中**名称**文本框中，键入的 Web 安装项目的名称。</span><span class="sxs-lookup"><span data-stu-id="8a351-110">In the **Name** text box, type a name for the Web Setup Project.</span></span> <span data-ttu-id="8a351-111">可以使用相同的名称为 ASP.NET Web 服务项目并添加"揰 _Setup"作为后缀，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8a351-111">You can use the same name as the ASP.NET Web Service project and add "_Setup" as a suffix and then click **OK**.</span></span>  
  
5. <span data-ttu-id="8a351-112">在解决方案资源管理器，右键单击新创建的 Web 安装项目节点，然后指向**视图**，然后单击**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="8a351-112">In Solution Explorer, right-click the newly created Web setup project node, and point to **View**, and then click **File System**.</span></span>  
  
6. <span data-ttu-id="8a351-113">在中**文件系统**窗口中，右键单击**Web 应用程序文件夹**节点，指向**添加**，然后单击**项目输出**。</span><span class="sxs-lookup"><span data-stu-id="8a351-113">In the **File System** window, right-click the **Web Application Folder** node and point to **Add**, then click **Project Output**.</span></span>  
  
7. <span data-ttu-id="8a351-114">在**添加项目输出组**对话框中，选择**主输出**并**内容文件**从 ASP.NET Web 服务项目，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="8a351-114">In the **Add Project Output Group** dialog box, select **Primary Output** and **Content Files** from the ASP.NET Web Service project and then click **OK**.</span></span>  
  
8. <span data-ttu-id="8a351-115">在解决方案资源管理器，展开**检测到依赖项**Web 安装项目下的节点。</span><span class="sxs-lookup"><span data-stu-id="8a351-115">In Solution Explorer, expand the **Detected Dependencies** node under the Web setup project.</span></span>  
  
9. <span data-ttu-id="8a351-116">选择所有的依赖项。</span><span class="sxs-lookup"><span data-stu-id="8a351-116">Select all dependencies.</span></span> <span data-ttu-id="8a351-117">在中**属性**窗口中，将**排除**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="8a351-117">In the **Properties** window, set the **Exclude** property to **True**.</span></span>  
  
10. <span data-ttu-id="8a351-118">生成 Web 安装项目。</span><span class="sxs-lookup"><span data-stu-id="8a351-118">Build your Web setup project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a351-119">有关创建 Web 安装项目的详细信息，请参阅"如何创建或添加 Web 安装项目"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62268 ](http://go.microsoft.com/fwlink/?LinkId=62268)。</span><span class="sxs-lookup"><span data-stu-id="8a351-119">For more information about creating Web setup projects, see "How to Create or Add a Web Setup Project" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a351-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a351-120">See Also</span></span>  
 [<span data-ttu-id="8a351-121">在无 Visual Studio 的计算机上部署已发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="8a351-121">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)