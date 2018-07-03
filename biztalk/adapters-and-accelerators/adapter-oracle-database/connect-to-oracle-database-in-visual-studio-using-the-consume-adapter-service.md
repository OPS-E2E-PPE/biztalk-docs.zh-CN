---
title: 连接到 Oracle 数据库，在 Visual Studio 中使用使用适配器服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Oracle database
- connection, to the Oracle database
ms.assetid: db2789d0-2d61-472b-ad0c-4ef0707e9c64
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19e83b518e188528b357e52f6397045baeb3ed76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010472"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a><span data-ttu-id="718a4-102">连接到 Visual Studio 中使用使用适配器服务中的 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="718a4-102">Connect to Oracle Database in Visual Studio using the Consume Adapter Service</span></span>
<span data-ttu-id="718a4-103">使用适配器服务外接程序被安装在安装 WCF LOB 适配器 SDK 时。</span><span class="sxs-lookup"><span data-stu-id="718a4-103">The Consume Adapter Service Add-in is installed when you install WCF LOB Adapter SDK.</span></span> <span data-ttu-id="718a4-104">使用适配器服务外接程序加载的计算机上安装的所有 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="718a4-104">The Consume Adapter Service Add-in loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="718a4-105">若要连接到使用基于 WCF 的 Oracle 数据库[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 BizTalk 项目中，必须使用**oracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="718a4-105">To connect to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in a BizTalk project, you must use the **oracleDBBinding**.</span></span>  

 <span data-ttu-id="718a4-106">本主题将说明了如何使用适配器服务外接程序使用。</span><span class="sxs-lookup"><span data-stu-id="718a4-106">This topic provides instructions on how to use the Consume Adapter Service Add-in.</span></span>  

## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="718a4-107">连接到 Oracle 数据库使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="718a4-107">Connecting to an Oracle Database Using the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="718a4-108">执行以下步骤连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="718a4-108">Perform the following steps to connect to an Oracle database using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

1. <span data-ttu-id="718a4-109">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="718a4-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="718a4-110">右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="718a4-110">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   2. <span data-ttu-id="718a4-111">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="718a4-111">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="718a4-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="718a4-112">Use this</span></span>    |             <span data-ttu-id="718a4-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="718a4-113">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="718a4-114">**类别**</span><span class="sxs-lookup"><span data-stu-id="718a4-114">**Categories**</span></span> | <span data-ttu-id="718a4-115">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="718a4-115">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="718a4-116">**模板**</span><span class="sxs-lookup"><span data-stu-id="718a4-116">**Templates**</span></span>  | <span data-ttu-id="718a4-117">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="718a4-117">Click **Consume Adapter Service**.</span></span> |


   3. <span data-ttu-id="718a4-118">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="718a4-118">Click **Add**.</span></span> <span data-ttu-id="718a4-119">此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="718a4-119">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="718a4-120">从**选择绑定**下拉列表中，选择**oracleDBBinding**然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="718a4-120">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="718a4-121">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="718a4-121">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  

   1. <span data-ttu-id="718a4-122">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="718a4-122">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="718a4-123">请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="718a4-123">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  

      - <span data-ttu-id="718a4-124">**用户名称**。</span><span class="sxs-lookup"><span data-stu-id="718a4-124">**User name**.</span></span> <span data-ttu-id="718a4-125">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="718a4-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="718a4-126">对 Oracle 数据库用户名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="718a4-126">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="718a4-127">应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。</span><span class="sxs-lookup"><span data-stu-id="718a4-127">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="718a4-128">通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写:"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="718a4-128">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  

      - <span data-ttu-id="718a4-129">**密码**。</span><span class="sxs-lookup"><span data-stu-id="718a4-129">**Password**.</span></span> <span data-ttu-id="718a4-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。</span><span class="sxs-lookup"><span data-stu-id="718a4-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="718a4-131">对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。</span><span class="sxs-lookup"><span data-stu-id="718a4-131">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  

   2. <span data-ttu-id="718a4-132">若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="718a4-132">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

4. <span data-ttu-id="718a4-133">单击**URI 属性**选项卡，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="718a4-133">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="718a4-134">有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="718a4-134">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

5. <span data-ttu-id="718a4-135">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="718a4-135">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="718a4-136">例如，如果你想要面向 POLLINGSTMT 操作，则必须设置**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="718a4-136">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="718a4-137">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="718a4-137">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

6. <span data-ttu-id="718a4-138">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="718a4-138">Click **OK**.</span></span>  

7. <span data-ttu-id="718a4-139">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="718a4-139">Click **Connect**.</span></span> <span data-ttu-id="718a4-140">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="718a4-140">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="718a4-141">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="718a4-141">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="718a4-142">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="718a4-142">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  

## <a name="see-also"></a><span data-ttu-id="718a4-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="718a4-143">See Also</span></span>  
 <span data-ttu-id="718a4-144">[连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="718a4-144">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="718a4-145">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="718a4-145">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)