---
title: "将证书添加到服务器上的证书存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a><span data-ttu-id="7cc63-102">将证书添加到服务器上的证书存储</span><span class="sxs-lookup"><span data-stu-id="7cc63-102">Adding Certificates to the Certificates Store on the Server</span></span>
<span data-ttu-id="7cc63-103">使用以下步骤将证书添加到服务器计算机上的证书 （本地计算机） 存储中的其他人文件夹。</span><span class="sxs-lookup"><span data-stu-id="7cc63-103">Use the following steps to add certificates to the Other People folder in the Certificates (Local Computer) store on the server computer.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="7cc63-104">若要将证书添加到证书存储</span><span class="sxs-lookup"><span data-stu-id="7cc63-104">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="7cc63-105">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BizTalk Accelerator for SWIFT 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BizTalk Accelerator for SWIFT Management Console**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7cc63-106">如果您还有 MMC 窗口中打开从前面的过程 （向客户端上的证书存储的添加证书），你可以将其用于此过程。</span><span class="sxs-lookup"><span data-stu-id="7cc63-106">If you still have the MMC window open from the previous procedure (Adding Certificates to the Certificates Store on the Client), you can use it for this procedure.</span></span>  
  
2.  <span data-ttu-id="7cc63-107">在管理控制台窗口中，展开**证书 （本地计算机）**文件夹，然后展开**其他人**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-107">In the Administration Console window, expand the **Certificates (Local Computer)** folder, and then expand **Other People**.</span></span>  
  
3.  <span data-ttu-id="7cc63-108">右键单击**证书**，指向**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-108">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
4.  <span data-ttu-id="7cc63-109">在欢迎使用证书导入向导页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-109">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7cc63-110">在导入页文件，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-110">On the File to Import page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="7cc63-111">在打开的对话框中，移动到您的证书，选择保存的文件位置**所有文件**为**文件类型**，选择你想要导入，然后单击证书**打开**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-111">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="7cc63-112">在导入页文件，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-112">On the File to Import page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="7cc63-113">在证书存储页中，确认**将所有证书都放入下列存储**是选择，验证**其他人**中显示**证书存储区**框中，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-113">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Other People** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="7cc63-114">在正在完成证书导入向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-114">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="7cc63-115">在证书导入向导对话框中，该值指示成功的导入，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7cc63-115">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
11. <span data-ttu-id="7cc63-116">对于其他证书将在消息修复和新的提交中使用重复步骤 3-10。</span><span class="sxs-lookup"><span data-stu-id="7cc63-116">Repeat steps 3 through 10 for all other certificates that you will use in message repair and new submission.</span></span>