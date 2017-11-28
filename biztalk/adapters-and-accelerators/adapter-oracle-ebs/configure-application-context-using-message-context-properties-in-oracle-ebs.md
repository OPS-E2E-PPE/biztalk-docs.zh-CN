---
title: "配置在 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51b76788-5c81-4bb4-8ef6-b1439955ea97
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43f0128b0d1da7ddfb9a29b697d5d5073f69dd33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a><span data-ttu-id="23f52-102">配置在 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文</span><span class="sxs-lookup"><span data-stu-id="23f52-102">Configure the application context using message context properties in Oracle E-Business Suite</span></span>
<span data-ttu-id="23f52-103">在使用 Oracle E-business Suite 项目上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须正确设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="23f52-103">To perform operations on Oracle E-Business Suite artifacts using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must set the application context appropriately.</span></span> <span data-ttu-id="23f52-104">你可以通过以下方式来设置应用程序上下文：</span><span class="sxs-lookup"><span data-stu-id="23f52-104">You can set the application context in the following ways:</span></span>  
  
-   <span data-ttu-id="23f52-105">通过指定适配器公开的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-105">By specifying the binding properties that the adapter exposes.</span></span> <span data-ttu-id="23f52-106">有关详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="23f52-106">For more information, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
-   <span data-ttu-id="23f52-107">通过使用适配器公开的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-107">By using message context properties that the adapter exposes.</span></span> <span data-ttu-id="23f52-108">通过使用消息上下文属性中设置应用程序上下文时，你必须考虑以下。</span><span class="sxs-lookup"><span data-stu-id="23f52-108">You must consider the following when setting the application context by using message context properties.</span></span>  
  
    -   <span data-ttu-id="23f52-109">你可以设置值仅对**ApplicationShortName**，**组织 Id**， **ResponsibilityKey**，和**ResponsibilityName**通过使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-109">You can set values only for **ApplicationShortName**, **OrganizationID**, **ResponsibilityKey**, and **ResponsibilityName** by using message context properties.</span></span> <span data-ttu-id="23f52-110">对于用户名和密码，必须使用的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-110">For the user name and password, you must use the binding properties.</span></span> <span data-ttu-id="23f52-111">为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-111">The value specified for the **ResponsibilityKey** message context property overrides the value specified for the **ResponsibilityName** message context property.</span></span>  
  
    -   <span data-ttu-id="23f52-112">如果你设置应用程序上下文使用的绑定属性和消息上下文属性，指定消息上下文属性的值优先，并覆盖指定的绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="23f52-112">If you set the application context using both the binding properties and message context properties, the values specified for message context properties take precedence and override the values specified for the binding properties.</span></span> <span data-ttu-id="23f52-113">但是，例如，如果指定为消息上下文属性，应用程序短名称和组织 ID 并承担相应责任名称为绑定属性，仅应用程序短名称的值均从消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-113">However, for example, if you specify the application short name as a message context property, and the organization ID and responsibility name as binding properties, only the value for the application short name is taken from the message context property.</span></span> <span data-ttu-id="23f52-114">从相关的绑定属性选取其余部分。</span><span class="sxs-lookup"><span data-stu-id="23f52-114">The rest are picked from the relevant binding properties.</span></span>  
  
 <span data-ttu-id="23f52-115">为何使用通过绑定属性设置的应用程序上下文的消息上下文属性？</span><span class="sxs-lookup"><span data-stu-id="23f52-115">Why use message context properties over binding properties to set the application context?</span></span> <span data-ttu-id="23f52-116">如果你设置使用绑定属性的应用程序上下文，则 WCF 自定义发送端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅可用于特定的组织 ID、 职责范围以及为绑定属性指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="23f52-116">If you set the application context using binding properties, the WCF-Custom send port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] can be used only for the specific organization ID, responsibility, and application that you specified for the binding properties.</span></span> <span data-ttu-id="23f52-117">相反，如果你使用的消息上下文属性，你可以配置"泛型"的 WCF 自定义发送端口，并在消息级别设置的应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="23f52-117">On the contrary, if you use the message context property, you can configure a “generic” WCF-Custom send port, and set the application context at the message level.</span></span>  
  
 <span data-ttu-id="23f52-118">适配器客户端必须设置该消息上下文属性对发送到 Oracle E-business Suite 以调用上 Oracle E-business Suite 操作的消息。</span><span class="sxs-lookup"><span data-stu-id="23f52-118">Adapter clients must set the message context properties on the message that is sent to Oracle E-Business Suite to invoke an operation on Oracle E-Business Suite.</span></span> <span data-ttu-id="23f52-119">中的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是不可变。</span><span class="sxs-lookup"><span data-stu-id="23f52-119">The messages in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] are immutable.</span></span> <span data-ttu-id="23f52-120">因此，客户端必须首先从现有的消息中，创建一条消息并将消息上下文属性对新的消息。</span><span class="sxs-lookup"><span data-stu-id="23f52-120">Hence, clients must first create a message from the existing message, and then set the message context properties on the new message.</span></span> <span data-ttu-id="23f52-121">有关本节中所述的过程，假定现有消息称为**请求**，新的消息称为**New_Request**。</span><span class="sxs-lookup"><span data-stu-id="23f52-121">For the procedure described in this section, assume that the existing message is called **Request**, and the new message is called **New_Request**.</span></span>  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a><span data-ttu-id="23f52-122">设置该消息，BizTalk 应用程序的上下文属性</span><span class="sxs-lookup"><span data-stu-id="23f52-122">Set the message context properties for BizTalk applications</span></span>  
  
1.  <span data-ttu-id="23f52-123">打开 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="23f52-123">Open the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="23f52-124">在解决方案资源管理器，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="23f52-124">In Solution Explorer, right-click **References**, and then click **Add References**.</span></span>  
  
3.  <span data-ttu-id="23f52-125">在**添加引用**对话框中，单击**浏览**选项卡上，然后浏览到位置其中 BizTalk 属性架构 DLL 为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可用。</span><span class="sxs-lookup"><span data-stu-id="23f52-125">In the **Add Reference** dialog box, click the **Browse** tab, and then browse to the location where the BizTalk property schema DLL for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is available.</span></span>  
  
     <span data-ttu-id="23f52-126">此 DLL， `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在\<*安装驱动器*>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。</span><span class="sxs-lookup"><span data-stu-id="23f52-126">This DLL, `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`, is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] at \<*installation drive*>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin.</span></span>  
  
4.  <span data-ttu-id="23f52-127">选择 DLL，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="23f52-127">Select the DLL, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="23f52-128">在 BizTalk 业务流程，添加一条消息， **New_Request**。</span><span class="sxs-lookup"><span data-stu-id="23f52-128">In the BizTalk orchestration, add a message, **New_Request**.</span></span> <span data-ttu-id="23f52-129">有关**消息类型**属性，请确保将相同的类型选择为现有的请求消息。</span><span class="sxs-lookup"><span data-stu-id="23f52-129">For the **Message Type** property, make sure you select the same type as the existing request message.</span></span>  
  
6.  <span data-ttu-id="23f52-130">在发送形状之前使用该消息发送到发送端口中，添加构造消息形状和在其中，消息赋值形状。</span><span class="sxs-lookup"><span data-stu-id="23f52-130">Before the Send shape using which the message is sent to the send port, add a Construct Message shape and within that, a Message Assignment shape.</span></span>  
  
7.  <span data-ttu-id="23f52-131">双击要打开的消息分配形状**BizTalk 表达式编辑器**。</span><span class="sxs-lookup"><span data-stu-id="23f52-131">Double-click the Message Assignment shape to open **BizTalk Expression Editor**.</span></span>  
  
8.  <span data-ttu-id="23f52-132">在**BizTalk 表达式编辑器**，添加以下内容，，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="23f52-132">In **BizTalk Expression Editor**, add the following, and then click **OK**:</span></span>  
  
    ```  
    New_Request = Request;  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="23f52-133">为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-133">The value specified for the **ResponsibilityKey** message context property overrides the value specified for the **ResponsibilityName** message context property.</span></span>  
  
9. <span data-ttu-id="23f52-134">请确保进一步处理的业务流程可通过使用**New_Request**消息。</span><span class="sxs-lookup"><span data-stu-id="23f52-134">Make sure further processing of the orchestration is done by using the **New_Request** message.</span></span>  
  
10. <span data-ttu-id="23f52-135">你可以部署在此业务流程之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须添加的程序集引用`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`BizTalk 应用程序将其中部署业务流程中。</span><span class="sxs-lookup"><span data-stu-id="23f52-135">Before you can deploy this orchestration in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must add the assembly reference for `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` in the BizTalk application where you will be deploying the orchestration.</span></span> <span data-ttu-id="23f52-136">若要部署中的程序集[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="23f52-136">To deploy an assembly in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="23f52-137">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="23f52-137">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    2.  <span data-ttu-id="23f52-138">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后你想要添加 BizTalk 程序集与应用程序。</span><span class="sxs-lookup"><span data-stu-id="23f52-138">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
    3.  <span data-ttu-id="23f52-139">右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。</span><span class="sxs-lookup"><span data-stu-id="23f52-139">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
    4.  <span data-ttu-id="23f52-140">在**添加资源**对话框中，单击**添加**，导航到包含 BizTalk 程序集文件，它是文件夹\<*安装驱动器*>: \程序 Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。</span><span class="sxs-lookup"><span data-stu-id="23f52-140">In the **Add Resources** dialog box, click **Add**, navigate to the folder containing the BizTalk assembly file, which is \<*installation drive*>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin.</span></span> <span data-ttu-id="23f52-141">选择`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="23f52-141">Select the `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` file, and then click **Open**.</span></span>  
  
    5.  <span data-ttu-id="23f52-142">上**选项**选项卡上，指定安装到全局程序集缓存 (GAC) 中，BizTalk 程序集的选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="23f52-142">On the **Options** tab, specify the options for installing the BizTalk assembly to the global assembly cache (GAC), and then click **OK**.</span></span>  
  
## <a name="set-the-language-for-performing-operations"></a><span data-ttu-id="23f52-143">设置执行操作的语言</span><span class="sxs-lookup"><span data-stu-id="23f52-143">Set the Language for Performing Operations</span></span>  
 <span data-ttu-id="23f52-144">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Oracle E-business Suite 的多语言支持 (MLS) 功能，允许你在执行操作时指定一种语言。</span><span class="sxs-lookup"><span data-stu-id="23f52-144">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports the Multi-Language Support (MLS) feature of Oracle E-Business Suite, and allows you to specify a language while performing operations.</span></span> <span data-ttu-id="23f52-145">适配器公开**语言**消息上下文属性可指定一种语言来执行操作。</span><span class="sxs-lookup"><span data-stu-id="23f52-145">The adapter exposes the **Language** message context property to specify a language for performing operations.</span></span>  
  
 <span data-ttu-id="23f52-146">为指定的值**语言**消息上下文属性将重写的值**语言**绑定下的属性**MlsSettings**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="23f52-146">The value specified for the **Language** message context property overrides the value of the **Language** binding property under the **MlsSettings** binding property.</span></span> <span data-ttu-id="23f52-147">有关详细信息**MlsSettings**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="23f52-147">For more information about the **MlsSettings** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
