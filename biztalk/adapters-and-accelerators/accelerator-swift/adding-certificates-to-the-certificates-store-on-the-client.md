---
title: 将证书添加到客户端上的证书存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 9e2722ee-dd6f-4b14-9796-2f2157e8cad2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a953ceaddd02df5e258ceb3034a29f6e56aff7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378895"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-client"></a><span data-ttu-id="46491-102">将证书添加到客户端上的证书存储</span><span class="sxs-lookup"><span data-stu-id="46491-102">Adding Certificates to the Certificates Store on the Client</span></span>
<span data-ttu-id="46491-103">使用以下步骤将证书添加到每个客户端计算机上的证书存储中的个人文件夹。</span><span class="sxs-lookup"><span data-stu-id="46491-103">Use the following steps to add certificates to the Personal folder in the certificates store on each client computer.</span></span> <span data-ttu-id="46491-104">必须将证书添加到证书-当前用户存储区中的个人文件夹。</span><span class="sxs-lookup"><span data-stu-id="46491-104">The certificates must be added to the Personal folder in the Certificates - Current User store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46491-105">如果您的证书不通过分发企业信任证书颁发机构，你必须导入到客户端计算机上的证书颁发机构的根证书。</span><span class="sxs-lookup"><span data-stu-id="46491-105">If your certificates are not distributed via an enterprise trusted Certification Authority, you must import the Certification Authority's root certificate onto the client computer(s).</span></span> <span data-ttu-id="46491-106">否则，您的个人证书将无法工作。</span><span class="sxs-lookup"><span data-stu-id="46491-106">Otherwise, your personal certificates will not work.</span></span> <span data-ttu-id="46491-107">证书颁发机构的证书导入到证书 （本地计算机） 节点中的受信任的根证书颁发机构文件夹中。</span><span class="sxs-lookup"><span data-stu-id="46491-107">Import the Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) node.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="46491-108">若要将证书添加到证书存储区</span><span class="sxs-lookup"><span data-stu-id="46491-108">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="46491-109">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="46491-109">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="46491-110">输入**mmc**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46491-110">Enter **mmc**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="46491-111">在 console1 对话框中，单击**文件**，然后单击**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="46491-111">In the Console1 dialog box, click **File**, and then click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="46491-112">在添加/删除管理单元对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="46491-112">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="46491-113">在添加独立管理单元对话框中，单击**证书**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="46491-113">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="46491-114">在证书管理单元对话框中，单击**我的用户帐户**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="46491-114">In the Certificates snap-in dialog box, click **My user account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="46491-115">在添加独立管理单元对话框中，单击**证书**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="46491-115">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="46491-116">在证书管理单元对话框中，单击**计算机帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="46491-116">In the Certificates snap-in dialog box, click **Computer account**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="46491-117">在选择计算机对话框中，请确保**本地计算机**已选中，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="46491-117">In the Select Computer dialog box, make sure **Local computer** is selected, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="46491-118">在添加独立管理单元对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="46491-118">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="46491-119">在添加/删除管理单元对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46491-119">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="46491-120">在中**控制台根节点**窗格中的控制台 1 对话框中，展开**证书-当前用户**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46491-120">In the **Console Root** pane of the Console1 dialog box, expand the **Certificates - Current User** folders.</span></span>  
  
12. <span data-ttu-id="46491-121">下**证书-当前用户**，展开**个人**。</span><span class="sxs-lookup"><span data-stu-id="46491-121">Under **Certificates - Current User**, expand **Personal**.</span></span>  
  
13. <span data-ttu-id="46491-122">右键单击**证书**，依次指向**的所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="46491-122">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
14. <span data-ttu-id="46491-123">在欢迎使用证书导入向导页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="46491-123">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
15. <span data-ttu-id="46491-124">在导入页的文件，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="46491-124">On the File to Import page, click **Browse**.</span></span>  
  
16. <span data-ttu-id="46491-125">在打开的对话框中，转到证书，请选择保存的文件位置**的所有文件**有关**Files of Type**，选择你想要导入，然后单击该证书**打开**。</span><span class="sxs-lookup"><span data-stu-id="46491-125">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
17. <span data-ttu-id="46491-126">在导入页的文件，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="46491-126">On the File to Import page, click **Next**.</span></span>  
  
18. <span data-ttu-id="46491-127">在证书存储页中，确认**将所有证书都放入下列存储**是选择，确保**个人**显示在**证书存储区**框中，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="46491-127">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Personal** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
19. <span data-ttu-id="46491-128">在正在完成证书导入向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="46491-128">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
20. <span data-ttu-id="46491-129">在证书导入向导对话框中，该值指示成功导入，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46491-129">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
21. <span data-ttu-id="46491-130">对于将在消息修复和新提交中使用其他证书重复步骤 13 到 20。</span><span class="sxs-lookup"><span data-stu-id="46491-130">Repeat steps 13 through 20 for all other certificates that you will use in message repair and new submission.</span></span>