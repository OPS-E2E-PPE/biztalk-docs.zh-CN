---
title: "如何： 创建一条路线动态将一条消息路由到电子邮件地址使用的 LDAP 查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751eaf381b762372652bb77ddf6f00ffe43971c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a><span data-ttu-id="72ea3-102">如何： 创建一条路线动态将一条消息路由到使用的 LDAP 查询的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="72ea3-102">How to: Create an Itinerary to Dynamically Route a Message to an Email Address Using an LDAP Query</span></span>
## <a name="goal"></a><span data-ttu-id="72ea3-103">目的</span><span class="sxs-lookup"><span data-stu-id="72ea3-103">Goal</span></span>  
 <span data-ttu-id="72ea3-104">本部分演示如何创建一条路线查询通过 LDAP （轻型目录访问协议） 的电子邮件地址，然后将电子邮件发送到使用 BizTalk Server SMTP 适配器解析终结点。</span><span class="sxs-lookup"><span data-stu-id="72ea3-104">This section demonstrates how to create an itinerary that queries an e-mail address through LDAP (Lightweight Directory Access Protocol) and then sends an e-mail message to the resolved endpoint using the BizTalk Server SMTP adapter.</span></span>  
  
 <span data-ttu-id="72ea3-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72ea3-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="72ea3-106">创建动态使用的 LDAP 查询将消息路由路线路由滑动。</span><span class="sxs-lookup"><span data-stu-id="72ea3-106">Create an itinerary routing slip to dynamically route a message using an LDAP query.</span></span>  
  
-   <span data-ttu-id="72ea3-107">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="72ea3-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="72ea3-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="72ea3-108">Prerequisites</span></span>  
 <span data-ttu-id="72ea3-109">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="72ea3-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
 <span data-ttu-id="72ea3-110">将在其完成此部分的计算机必须安装 Microsoft Active Directory 目录服务配置并且正在运行 (它不是所需计算机是域控制器，但必须连接到域)。</span><span class="sxs-lookup"><span data-stu-id="72ea3-110">The computer on which you will complete this section must have Microsoft Active Directory directory service configured and running (it is not required that the computer is the domain controller, but it must be connected to the domain).</span></span> <span data-ttu-id="72ea3-111">此外，SMTP 服务器必须已配置并且正在运行;若要测试本操作指南主题的结果，您必须具有其进行检查 ESB 所发送的电子邮件的客户端。</span><span class="sxs-lookup"><span data-stu-id="72ea3-111">Also, an SMTP server must be configured and running; in order to test the outcome of this How-to topic, you must have a client with which to check the e-mail sent by the ESB.</span></span>  
  
 <span data-ttu-id="72ea3-112">本部分中的说明假定组织名全局 Bank globalbank.com，域为使用 Active Directory 组织单位名为 Employees 包含名 John Evans 为使用有效的电子邮件地址 （如其配置文件中的用户johne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="72ea3-112">The instructions in this section assume an organization named Global Bank, with a domain of globalbank.com, with an Active Directory Organizational Unit named Employees that contains a user named John Evans with a valid e-mail address in his profile (such as johne@globalbank.com).</span></span> <span data-ttu-id="72ea3-113">不需要复制这些环境因素;但是，为了进行重新创建你的环境中的此实现，请考虑这些因素并根据需要替换。</span><span class="sxs-lookup"><span data-stu-id="72ea3-113">It is not necessary to replicate these environmental factors; however, for purposes of recreating this implementation in your environment, please account for these factors and make substitutions as necessary.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="72ea3-114">步骤</span><span class="sxs-lookup"><span data-stu-id="72ea3-114">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a><span data-ttu-id="72ea3-115">若要创建 ESB 路线域特定语言 (DSL) 模型</span><span class="sxs-lookup"><span data-stu-id="72ea3-115">To create an ESB itinerary domain-specific language (DSL) model</span></span>  
  
1.  <span data-ttu-id="72ea3-116">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="72ea3-116">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="72ea3-117">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-117">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="72ea3-118">在**添加新项**对话框中，键入**LdapResolution**中**名称**框中，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-118">In the **Add New Item** dialog box, type **LdapResolution** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="72ea3-119">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="72ea3-119">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="72ea3-120">在 Visual Studio 中，单击的设计图面**LdapResolution.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-120">In Visual Studio, click the design surface of **LdapResolution.itinerary**.</span></span> <span data-ttu-id="72ea3-121">在**LdapResolution**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-121">In the **LdapResolution** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-122">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-123">下**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="72ea3-123">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="72ea3-124">在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\LdapResolution**中**文件名**框中，并依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-124">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\LdapResolution** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="72ea3-125">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="72ea3-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="72ea3-126">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="72ea3-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="72ea3-127">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="72ea3-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="72ea3-128">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="72ea3-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="72ea3-129">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="72ea3-130">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-131">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-132">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-133">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="72ea3-134">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="72ea3-135">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="72ea3-136">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-137">单击**名称**属性，再然后键入**RouteMessageEmail**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-137">Click the **Name** property, and then type **RouteMessageEmail**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-138">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="72ea3-139">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="72ea3-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="72ea3-140">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-141">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="72ea3-142">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="72ea3-143">右键单击**冲突解决程序**集合**RouteMessageEmail**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-143">Right-click the **Resolver** collection of the **RouteMessageEmail** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="72ea3-144">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-145">单击**名称**属性，再然后键入**LdapResolver**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-145">Click the **Name** property, and then type **LdapResolver**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-146">在**解析程序实现**下拉列表中，单击**LDAP 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-146">In the **Resolver Implementation** drop-down list, click **LDAP Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-147">在**传输名称**下拉列表中，单击**SMTP**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-147">In the **Transport Name** drop-down list, click **SMTP**.</span></span>  
  
    4.  <span data-ttu-id="72ea3-148">单击**传输位置**属性，再然后键入**{邮件}**</span><span class="sxs-lookup"><span data-stu-id="72ea3-148">Click the **Transport Location** property, and then type **{mail}**</span></span>  
  
    5.  <span data-ttu-id="72ea3-149">单击**SearchRoot**属性，再然后键入**ou = 员工，dc = globalbank，dc = com**</span><span class="sxs-lookup"><span data-stu-id="72ea3-149">Click the **SearchRoot** property, and then type **ou=Employees,dc=globalbank,dc=com**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="72ea3-150">如果你未在"先决条件"部分中设置你的环境根据规范，将替换那些适用于你的环境中的上述属性的值。</span><span class="sxs-lookup"><span data-stu-id="72ea3-150">If you have not set up your environment according to the specifications in the "Prerequisites" section, replace the values in the preceding property with ones that are appropriate for your environment.</span></span>  
  
    6.  <span data-ttu-id="72ea3-151">单击**筛选器**属性，然后将更改为值**(&(objectClass=User) (&#124;(givenName=john)))**</span><span class="sxs-lookup"><span data-stu-id="72ea3-151">Click the **Filter** property, and then change the value to **(&(objectClass=User)(&#124;(givenName=john)))**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="72ea3-152">键入要替换现有文本的前面的值。</span><span class="sxs-lookup"><span data-stu-id="72ea3-152">Type the preceding value to replace the existing text.</span></span>  
  
    7.  <span data-ttu-id="72ea3-153">在**ThrowErrorIfNotFound**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-153">In the **ThrowErrorIfNotFound** drop-down list, click **True**.</span></span>  
  
4.  <span data-ttu-id="72ea3-154">在属性窗口中，单击**终结点配置**属性，然后单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="72ea3-154">In the Properties window, click the **Endpoint Configuration** property, and then click the ellipsis button (...).</span></span>  
  
    1.  <span data-ttu-id="72ea3-155">在**终结点配置**对话框中，单击**EmailBodyText**属性，再然后键入**顺序已准备好处理**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-155">In the **Endpoint Configuration** dialog box, click the **EmailBodyText** property, and then type **Order is ready to be processed**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-156">单击**从**属性，再然后键入 **orders@globalbank.com** 。</span><span class="sxs-lookup"><span data-stu-id="72ea3-156">Click the **From** property, and then type **orders@globalbank.com**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-157">单击**MessagePartsAttachment**属性，再然后键入**2**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-157">Click the **MessagePartsAttachment** property, and then type **2**.</span></span>  
  
    4.  <span data-ttu-id="72ea3-158">单击**主题**属性，再然后键入**{givenName} 的顺序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-158">Click the **Subject** property, and then type **Order for {givenName}**.</span></span>  
  
    5.  <span data-ttu-id="72ea3-159">配置**SMTPAuthentication、 SMTPHost、 用户名、**和**密码**针对本地环境中使用的连接信息的属性。</span><span class="sxs-lookup"><span data-stu-id="72ea3-159">Configure the **SMTPAuthentication, SMTPHost, UserName,** and **Password** properties using the connection information for your local environment.</span></span>  
  
    6.  <span data-ttu-id="72ea3-160">单击**确定**关闭**终结点配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="72ea3-160">Click **OK** to close the **Endpoint Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="72ea3-161">右键单击**LdapResolver**冲突解决程序，，然后单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-161">Right-click the **LdapResolver** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
6.  <span data-ttu-id="72ea3-162">在输出窗口中，验证中已解析的主题**终结点配置**值是**john 顺序**，然后确认已解析**传输位置**是电子邮件地址与在 Active Directory 中的用户的帐户相关联 (例如， johne@globalbank.com)。</span><span class="sxs-lookup"><span data-stu-id="72ea3-162">In the Output window, verify the subject in the resolved **Endpoint Configuration** value is **Order for John**, and then verify that the resolved **Transport Location** is the e-mail address associated with the user's account in Active Directory (for example, johne@globalbank.com).</span></span>  
  
7.  <span data-ttu-id="72ea3-163">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-163">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="72ea3-164">将从连接**ReceiveNAOrder**到模型元素**RouteMessageEmail**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-164">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessageEmail** model element.</span></span>  
  
8.  <span data-ttu-id="72ea3-165">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteMessageEmail**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-165">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteMessageEmail** model element.</span></span> <span data-ttu-id="72ea3-166">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-166">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-167">单击**名称**属性，再然后键入**EmailNAOrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-167">Click the **Name** property, and then type **EmailNAOrderDoc**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-168">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-168">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-169">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-169">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="72ea3-170">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-170">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
9. <span data-ttu-id="72ea3-171">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteMessageEmail**模型元素和**EmailNAOrderDoc**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-171">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteMessageEmail** model element and the **EmailNAOrderDoc** model element.</span></span> <span data-ttu-id="72ea3-172">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="72ea3-172">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="72ea3-173">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-173">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="72ea3-174">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-174">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="72ea3-175">在**关闭负载增加**下拉列表中，展开**EmailNAOrderDoc**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-175">In the **Off-Ramp** drop-down list, expand **EmailNAOrderDoc**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="72ea3-176">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-176">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="72ea3-177">将从连接**RouteMessageEmail**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-177">Drag a connection from the **RouteMessageEmail** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="72ea3-178">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-178">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="72ea3-179">将从连接**SendPortFilter**到模型元素**EmailNAOrderDoc**模型元素。</span><span class="sxs-lookup"><span data-stu-id="72ea3-179">Drag a connection from the **SendPortFilter** model element to the **EmailNAOrderDoc** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="72ea3-180">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="72ea3-180">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="72ea3-181">在 Visual Studio 中，右键单击的设计图面**LdapResolution**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-181">In Visual Studio, right-click the design surface of the **LdapResolution** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72ea3-182">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="72ea3-182">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="72ea3-183">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="72ea3-183">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="72ea3-184">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (LdapResolution.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="72ea3-184">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (LdapResolution.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="72ea3-185">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="72ea3-185">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="72ea3-186">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="72ea3-186">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="72ea3-187">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="72ea3-187">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="72ea3-188">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="72ea3-188">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="72ea3-189">选择**LdapResolution.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="72ea3-189">Select **LdapResolution.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="72ea3-190">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="72ea3-190">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="72ea3-191">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="72ea3-191">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="72ea3-192">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="72ea3-192">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="72ea3-193">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="72ea3-193">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="72ea3-194">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="72ea3-194">Click the **Submit Request** button.</span></span> <span data-ttu-id="72ea3-195">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="72ea3-195">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="72ea3-196">打开 Microsoft Outlook Express （或所选邮件客户端） 并验证到 John Evans 的电子邮件的消息传递。</span><span class="sxs-lookup"><span data-stu-id="72ea3-196">Open Microsoft Outlook Express (or the mail client of your choice) and verify delivery of the message to the e-mail of John Evans.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="72ea3-197">其他资源</span><span class="sxs-lookup"><span data-stu-id="72ea3-197">Additional Resources</span></span>  
 <span data-ttu-id="72ea3-198">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="72ea3-198">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="72ea3-199">开发活动</span><span class="sxs-lookup"><span data-stu-id="72ea3-199">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="72ea3-200">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="72ea3-200">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)