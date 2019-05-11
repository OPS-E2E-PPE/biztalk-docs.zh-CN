---
title: 第 2 步：部署 Web 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39a8b60918f2dd97ea9442fca5dda961e2cafde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363269"
---
# <a name="step-2-deploy-the-web-project"></a><span data-ttu-id="803f0-102">第 2 步：部署 Web 项目</span><span class="sxs-lookup"><span data-stu-id="803f0-102">Step 2: Deploy the Web Project</span></span>
<span data-ttu-id="803f0-103">![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="803f0-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="803f0-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="803f0-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="803f0-105">在此步骤中将发布 Web 项目中生成[步骤 1:使用适配器服务开发向导创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)到 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="803f0-105">In this step you will publish the Web project generated in [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) to Internet Information Services (IIS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="803f0-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="803f0-106">Prerequisites</span></span>  
 <span data-ttu-id="803f0-107">若要完成此步骤中，应当已完成[步骤 1:使用适配器服务开发向导创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)。</span><span class="sxs-lookup"><span data-stu-id="803f0-107">To complete this step, you should have completed [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md).</span></span> <span data-ttu-id="803f0-108">你的 Web 服务器还必须安装以启用 HTTPS 通信的 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="803f0-108">Your Web server must also have an SSL certificate installed to enable HTTPS communication.</span></span>  
  
## <a name="compile-and-deploy-the-web-project"></a><span data-ttu-id="803f0-109">编译和部署 Web 项目</span><span class="sxs-lookup"><span data-stu-id="803f0-109">Compile and deploy the Web project</span></span>  
  
1. <span data-ttu-id="803f0-110">在 Visual Studio 中，加载以前创建的 EchoWeb 项目。</span><span class="sxs-lookup"><span data-stu-id="803f0-110">In Visual Studio, load the EchoWeb project created previously.</span></span>  
  
2. <span data-ttu-id="803f0-111">打开 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="803f0-111">Open a Visual Studio command prompt.</span></span>  
  
3. <span data-ttu-id="803f0-112">在命令提示符下从 C:\tutorials\echoweb 文件夹中，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="803f0-112">At the command prompt, from the C:\tutorials\echoweb folder, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="803f0-113">**sn /k EchoWebKey.snk**</span><span class="sxs-lookup"><span data-stu-id="803f0-113">**sn /k EchoWebKey.snk**</span></span>  
  
    <span data-ttu-id="803f0-114">一条确认消息，**密钥对写入到 EchoWebKey.snk**，显示在命令行上。</span><span class="sxs-lookup"><span data-stu-id="803f0-114">A confirmation message, **Key pair written to EchoWebKey.snk**, displays on the command line.</span></span>  
  
4. <span data-ttu-id="803f0-115">关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="803f0-115">Close the command prompt.</span></span>  
  
5. <span data-ttu-id="803f0-116">在中**解决方案资源管理器**，右键单击 EchoWeb 项目，然后选择**发布网站**。</span><span class="sxs-lookup"><span data-stu-id="803f0-116">In **Solution Explorer**, right click the EchoWeb project, and then select **Publish Web Site**.</span></span>  
  
6. <span data-ttu-id="803f0-117">在中**发布网站**对话框中，对于**目标位置**，输入**http://machinename/EchoWeb**。</span><span class="sxs-lookup"><span data-stu-id="803f0-117">In the **Publish Web Site** dialog box, for **Target location**, enter **http://machinename/EchoWeb**.</span></span> <span data-ttu-id="803f0-118">选择**允许可更新此预编译的站点**，**使用固定命名和单页程序集**，并**启用强命名在预编译程序集**。</span><span class="sxs-lookup"><span data-stu-id="803f0-118">Select **Allow this precompiled site to be updatable**, **Use fixed naming and single page assemblies**, and **Enable strong naming on precompiled assemblies**.</span></span> <span data-ttu-id="803f0-119">在中**密钥文件位置**字段中，单击省略号 **（...）** 按钮，选择以前创建的 EchoWebKey.snk 文件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="803f0-119">In the **Key file location** field, click the ellipsis **(…)** button, select the EchoWebKey.snk file created previously, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="803f0-120">若要验证是否已正确创建网站，启动 Internet Explorer 中，输入 **"<http://localhost/EchoWeb/EchoOutboundContract.svc>"** 中地址栏中，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="803f0-120">To verify that the Web site was correctly created, start Internet Explorer, enter  **"<http://localhost/EchoWeb/EchoOutboundContract.svc>"** in the address bar, and then press ENTER.</span></span> <span data-ttu-id="803f0-121">应显示一个页面，介绍 EchoOutboundContractClient。</span><span class="sxs-lookup"><span data-stu-id="803f0-121">A Web page that describes the EchoOutboundContractClient should appear.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="803f0-122">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="803f0-122">What did I just do?</span></span>  
 <span data-ttu-id="803f0-123">你只是 Web 项目发布到 IIS。</span><span class="sxs-lookup"><span data-stu-id="803f0-123">You have just published your Web project to IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="803f0-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="803f0-124">Next Steps</span></span>  
 <span data-ttu-id="803f0-125">现在，已编译并部署该项目，你可以转到[步骤 3:创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span><span class="sxs-lookup"><span data-stu-id="803f0-125">Now that you have compiled and deployed the project, you can proceed to [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803f0-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="803f0-126">See Also</span></span>  
 [<span data-ttu-id="803f0-127">教程 3：在 IIS 中托管 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="803f0-127">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)