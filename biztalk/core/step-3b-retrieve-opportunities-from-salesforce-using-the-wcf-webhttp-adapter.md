---
title: 步骤 3b： 检索机会从 Salesforce 使用 WCF WebHttp 适配器的详细信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 115c908f-777b-4c51-85ea-71d639b01775
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05312890d7cd21810651e7e41a8418080912f72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279549"
---
# <a name="step-3b-retrieve-opportunity-details-from-salesforce-using-the-wcf-webhttp-adapter"></a><span data-ttu-id="651c7-102">步骤 3b： 检索机会从 Salesforce 使用 WCF WebHttp 适配器的详细信息</span><span class="sxs-lookup"><span data-stu-id="651c7-102">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>
<span data-ttu-id="651c7-103">在本部分中，我们将改进业务流程，以处理传入的机会通知，从通知中提取机会名称，并使用该名称创建请求查询，以发送到 Salesforce。</span><span class="sxs-lookup"><span data-stu-id="651c7-103">In this section, we’ll enhance the orchestration to process the incoming opportunity notification, extract the opportunity name from the notification, and use that to create a request query to send to Salesforce.</span></span> <span data-ttu-id="651c7-104">此请求检索与机会关联的产品的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="651c7-104">This retrieves specific details about the products associated with the opportunity.</span></span> <span data-ttu-id="651c7-105">来自 Salesforce 的查询响应将接收回 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="651c7-105">The query response from Salesforce is received back into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="651c7-106">为此，我们将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="651c7-106">To achieve this, we’ll perform the following steps:</span></span>  
  
-   <span data-ttu-id="651c7-107">创建用于向 Salesforce 发送查询消息的架构和消息变量。</span><span class="sxs-lookup"><span data-stu-id="651c7-107">Create a schema and message variables to send a query message to Salesforce.</span></span>  
  
-   <span data-ttu-id="651c7-108">创建映射，以使用机会通知中的值创建查询，来检索与机会关联的产品详细信息。</span><span class="sxs-lookup"><span data-stu-id="651c7-108">Create a map to use the values from the opportunity notification for creating a query to retrieve product details associated with the opportunity.</span></span>  
  
-   <span data-ttu-id="651c7-109">创建用于从 Salesforce 接收查询响应的架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-109">Create a schema to receive a query response from Salesforce.</span></span>  
  
-   <span data-ttu-id="651c7-110">为请求和响应架构创建消息变量。</span><span class="sxs-lookup"><span data-stu-id="651c7-110">Create message variables for the request and response schemas.</span></span>  
  
## <a name="create-schema-and-message-variables-to-send-query-messages-to-salesforce"></a><span data-ttu-id="651c7-111">创建用于向 Salesforce 发送查询消息的架构和消息变量</span><span class="sxs-lookup"><span data-stu-id="651c7-111">Create Schema and Message Variables to Send Query Messages to Salesforce</span></span>  
 <span data-ttu-id="651c7-112">若要使用通过机会通知提供的信息从 Salesforce 检索产品详细信息，我们需要向 Salesforce 发送查询。</span><span class="sxs-lookup"><span data-stu-id="651c7-112">To retrieve product details from Salesforce by using the information available through an Opportunity notification, we need to send a query to Salesforce.</span></span> <span data-ttu-id="651c7-113">查询将作为一条 XML 消息发送到 Salesforce。</span><span class="sxs-lookup"><span data-stu-id="651c7-113">The query is sent to Salesforce as an XML message.</span></span> <span data-ttu-id="651c7-114">因此，在下面的过程中，我们将创建请求消息架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-114">So, in the following procedure we create a schema for the request message.</span></span> <span data-ttu-id="651c7-115">在随后的过程中，我们会将机会通知架构与此架构相映射，以构造用于检索机会的产品详细信息的查询。</span><span class="sxs-lookup"><span data-stu-id="651c7-115">In the subsequent procedure, we will map the opportunity notification schema with this schema to construct a query for retrieving product details for the opportunity.</span></span>  
  
#### <a name="to-create-a-schema-for-sending-query-request"></a><span data-ttu-id="651c7-116">创建用于发送查询请求的架构</span><span class="sxs-lookup"><span data-stu-id="651c7-116">To create a schema for sending query request</span></span>  
  
1.  <span data-ttu-id="651c7-117">向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-117">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="651c7-118">将其命名为 `QueryRequest.xsd`。</span><span class="sxs-lookup"><span data-stu-id="651c7-118">Name it `QueryRequest.xsd`.</span></span>  
  
2.  <span data-ttu-id="651c7-119">重命名根节点到`QueryRequest`。</span><span class="sxs-lookup"><span data-stu-id="651c7-119">Rename the root node to `QueryRequest`.</span></span> <span data-ttu-id="651c7-120">添加 QueryRequest 记录下的子字段元素并将其命名`Query`。</span><span class="sxs-lookup"><span data-stu-id="651c7-120">Add a child field element under the QueryRequest record and name it `Query`.</span></span>  
  
3.  <span data-ttu-id="651c7-121">将提升**查询**使之可在业务流程中使用的架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="651c7-121">Promote the **Query** element in the schema so that it is available for use within the orchestration.</span></span> <span data-ttu-id="651c7-122">在后面的步骤中，我们将使用此已升级的元素分配查询字符串。</span><span class="sxs-lookup"><span data-stu-id="651c7-122">In the later steps we will use this promoted element to assign the query string.</span></span>  
  
     <span data-ttu-id="651c7-123">右键单击**查询**元素，指向**Promote**，然后单击**快速提升**。</span><span class="sxs-lookup"><span data-stu-id="651c7-123">Right-click the **Query** element, point to **Promote**, and then click **Quick Promotions**.</span></span> <span data-ttu-id="651c7-124">这会导致创建**PropertySchema.xsd**具有架构**查询**元素。</span><span class="sxs-lookup"><span data-stu-id="651c7-124">This results in creating a **PropertySchema.xsd** schema with a **Query** element.</span></span> <span data-ttu-id="651c7-125">请记下 PropertySchema 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="651c7-125">Note the namespace for the PropertySchema.</span></span> <span data-ttu-id="651c7-126">在以后的步骤中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置物理端口时，你将需要此信息。</span><span class="sxs-lookup"><span data-stu-id="651c7-126">You will need this in the future steps while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="651c7-127">保存所有更改。</span><span class="sxs-lookup"><span data-stu-id="651c7-127">Save all changes.</span></span>  
  
## <a name="map-the-opportunity-notification-schema-to-the-query-schema"></a><span data-ttu-id="651c7-128">将机会通知架构映射到查询架构</span><span class="sxs-lookup"><span data-stu-id="651c7-128">Map the Opportunity Notification Schema to the Query Schema</span></span>  
 <span data-ttu-id="651c7-129">若要检索与机会关联的产品详细信息，我们需要向 Salesforce 发送如下查询：</span><span class="sxs-lookup"><span data-stu-id="651c7-129">To retrieve the product details associated with the opportunity, we need to send a query similar to the following to Salesforce:</span></span>  
  
```  
SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '<opportunity_name>'  
```  
  
 <span data-ttu-id="651c7-130">在前面的过程中，我们已创建了查询消息架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-130">In the previous procedure we already created the schema of the query message.</span></span> <span data-ttu-id="651c7-131">在此过程中，我们将机会通知架构映射到查询请求架构，并使用 functoid 构造此查询。</span><span class="sxs-lookup"><span data-stu-id="651c7-131">In this procedure, we map the opportunity notification schema to the query request schema and use functoids to construct this query.</span></span> <span data-ttu-id="651c7-132">此查询将作为和的值传递**查询**中的元素**QueryRequest.xsd**架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-132">This query will be passed as a value to the **Query** element in the **QueryRequest.xsd** schema.</span></span>  
  
#### <a name="to-map-the-opportunity-notification"></a><span data-ttu-id="651c7-133">映射机会通知</span><span class="sxs-lookup"><span data-stu-id="651c7-133">To map the opportunity notification</span></span>  
  
1.  <span data-ttu-id="651c7-134">向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目添加映射。</span><span class="sxs-lookup"><span data-stu-id="651c7-134">Add a map to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="651c7-135">对图命名`Notification_QueryRequest.btm`。</span><span class="sxs-lookup"><span data-stu-id="651c7-135">Name the map `Notification_QueryRequest.btm`.</span></span>  
  
2.  <span data-ttu-id="651c7-136">将源架构设置为**NotificationService_soap_sforce_com_2005_09_outbound.xsd**。</span><span class="sxs-lookup"><span data-stu-id="651c7-136">Set the source schema to **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span> <span data-ttu-id="651c7-137">将目标架构设置为**QueryRequest**.xsd。</span><span class="sxs-lookup"><span data-stu-id="651c7-137">Set the destination schema to **QueryRequest**.xsd.</span></span>  
  
3.  <span data-ttu-id="651c7-138">添加**字符串连接**functoid 到映射图面。</span><span class="sxs-lookup"><span data-stu-id="651c7-138">Add a **String Concatenate** functoid to the mapping surface.</span></span> <span data-ttu-id="651c7-139">打开**配置字符串串联 Functoid**对话框框中，并指定输入的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="651c7-139">Open the **Configure String Concatenate Functoid** dialog box and specify the input values as follows:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="651c7-140">Input[0]</span><span class="sxs-lookup"><span data-stu-id="651c7-140">Input[0]</span></span>|<span data-ttu-id="651c7-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span><span class="sxs-lookup"><span data-stu-id="651c7-141">SELECT Amount, Id, Name,(SELECT Quantity, ListPrice, PricebookEntry.UnitPrice, PricebookEntry.Name FROM OpportunityLineItems) FROM Opportunity Where Name = '</span></span>|  
    |<span data-ttu-id="651c7-142">输入 [1]</span><span class="sxs-lookup"><span data-stu-id="651c7-142">Input[1]</span></span>|<span data-ttu-id="651c7-143">将源架构中的 Name 元素连接到 functoid，以使用 Name 元素的值作为第二个输入。</span><span class="sxs-lookup"><span data-stu-id="651c7-143">Connect the Name element in the source schema to the functoid to use the value of the Name element as the second input.</span></span>|  
    |<span data-ttu-id="651c7-144">输入 [2]</span><span class="sxs-lookup"><span data-stu-id="651c7-144">Input[2]</span></span>|<span data-ttu-id="651c7-145">**注意：** 对于最后一个输入值，指定仅右单引号 （'）。</span><span class="sxs-lookup"><span data-stu-id="651c7-145">' **Note:**  For the last input value, specify only a closing single quote (').</span></span>|  
  
     <span data-ttu-id="651c7-146">下面的屏幕截图描绘了配置为**字符串连接**functoid。</span><span class="sxs-lookup"><span data-stu-id="651c7-146">The following screenshot depicts the configuration for the **String Concatenate** functoid.</span></span>  
  
     <span data-ttu-id="651c7-147">![配置字符串连接 functoid](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span><span class="sxs-lookup"><span data-stu-id="651c7-147">![Configure String Concatenate functoid](../core/media/bts-sf-stringconcatenate.jpg "BTS_SF_StringConcatenate")</span></span>  
  
     <span data-ttu-id="651c7-148">当三个输入参数连接在一起时，将形成要发送到 Salesforce 的所需查询。</span><span class="sxs-lookup"><span data-stu-id="651c7-148">When the three input parameters are concatenated, it will form the required query to be sent to Salesforce.</span></span>  
  
4.  <span data-ttu-id="651c7-149">将“字符串连接”functoid 连接到目标架构中的 Query 元素，如下面的屏幕快照中所示。</span><span class="sxs-lookup"><span data-stu-id="651c7-149">Connect the String Concatenate functoid to the Query element in the destination schema, as shown in the following screenshot.</span></span>  
  
     <span data-ttu-id="651c7-150">![映射到查询架构通知响应](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span><span class="sxs-lookup"><span data-stu-id="651c7-150">![Map notification response to query schema](../core/media/bts-sf-notification-query-mapping.jpg "BTS_SF_Notification_Query_Mapping")</span></span>  
  
5.  <span data-ttu-id="651c7-151">保存对映射所做的更改。</span><span class="sxs-lookup"><span data-stu-id="651c7-151">Save changes to the map.</span></span>  
  
## <a name="creating-schema-to-receive-the-query-response-message"></a><span data-ttu-id="651c7-152">创建用于接收查询响应消息的架构</span><span class="sxs-lookup"><span data-stu-id="651c7-152">Creating Schema to Receive the Query Response Message</span></span>  
 <span data-ttu-id="651c7-153">在本部分中，我们将创建用于从 Salesforce 接收查询响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-153">In this section, we create the schema to receive the query response message from Salesforce.</span></span> <span data-ttu-id="651c7-154">在本部分中，我们将手动创建查询响应架构。</span><span class="sxs-lookup"><span data-stu-id="651c7-154">In this section, we manually create the schema for the query response.</span></span>  
  
#### <a name="to-create-a-schema-to-receive-the-query-response"></a><span data-ttu-id="651c7-155">创建用于接收查询响应的架构</span><span class="sxs-lookup"><span data-stu-id="651c7-155">To create a schema to receive the query response</span></span>  
  
1.  <span data-ttu-id="651c7-156">添加到新架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目并将其命名`QueryResult.xsd`。</span><span class="sxs-lookup"><span data-stu-id="651c7-156">Add a new schema to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project and name it `QueryResult.xsd`.</span></span>  
  
2.  <span data-ttu-id="651c7-157">Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017)对象描述了从 Salesforce 收到查询响应。</span><span class="sxs-lookup"><span data-stu-id="651c7-157">The Salesforce [QueryResult](http://go.microsoft.com/fwlink/?LinkId=287017) object depicts the query response received from Salesforce.</span></span> <span data-ttu-id="651c7-158">因此，我们将构建一个描述以下内容的架构：</span><span class="sxs-lookup"><span data-stu-id="651c7-158">So, we’ll build a schema to depict the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16" ?>  
    - <xs:schema xmlns="http://BtsSalesforceIntegration.QueryResult" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://BtsSalesforceIntegration.QueryResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      - <xs:element name="QueryResult">  
        - <xs:complexType>  
          - <xs:sequence>  
            <xs:element name="done" type="xs:string" />  
            - <xs:sequence>  
              - <xs:element name="records">  
                - <xs:complexType>  
                  - <xs:sequence>  
                    <xs:element name="Id" type="xs:string" />  
                    <xs:element name="Amount" type="xs:string" />  
                    <xs:element name="Name" type="xs:string" />  
                    - <xs:sequence>  
                      - <xs:element name="OpportunityLineItems">  
                        - <xs:complexType>  
                          - <xs:sequence>  
                            <xs:element name="done" type="xs:string" />  
                            - <xs:sequence minOccurs="1" maxOccurs="unbounded">  
                              - <xs:element name="records">  
                                - <xs:complexType>  
                                  - <xs:sequence>  
                                    <xs:element name="Quantity" type="xs:string" />  
                                    <xs:element name="ListPrice" type="xs:string" />  
                                    - <xs:element name="PricebookEntry">  
                                      - <xs:complexType>  
                                        - <xs:sequence>  
                                          <xs:element name="UnitPrice" type="xs:string" />  
                                          <xs:element name="Name" type="xs:string" />  
                                        </xs:sequence>  
                                        <xs:attribute name="type" type="xs:string" />  
                                        <xs:attribute name="url" type="xs:string" />  
                                      </xs:complexType>  
                                    </xs:element>  
                                  </xs:sequence>  
                                  <xs:attribute name="type" type="xs:string" />  
                                  <xs:attribute name="url" type="xs:string" />  
                                </xs:complexType>  
                              </xs:element>  
                            </xs:sequence>  
                            <xs:element name="totalSize" type="xs:string" />  
                          </xs:sequence>  
                        </xs:complexType>  
                      </xs:element>  
                    </xs:sequence>  
                  </xs:sequence>  
                  <xs:attribute name="type" type="xs:string" />  
                  <xs:attribute name="url" type="xs:string" />  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
            <xs:element name="totalSize" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
     <span data-ttu-id="651c7-159">架构结构应如下所示：</span><span class="sxs-lookup"><span data-stu-id="651c7-159">The schema structure should look like the following:</span></span>  
  
     <span data-ttu-id="651c7-160">![来自 Salesforce 的查询响应架构](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span><span class="sxs-lookup"><span data-stu-id="651c7-160">![Schema for query response from Salesforce](../core/media/bts-sf-queryresult.jpg "BTS_SF_QueryResult")</span></span>  
  
3.  <span data-ttu-id="651c7-161">保存对架构所做的更改。</span><span class="sxs-lookup"><span data-stu-id="651c7-161">Save changes to the schema.</span></span>  
  
## <a name="create-message-variables-for-queryrequest-and-queryresult-schemas"></a><span data-ttu-id="651c7-162">为 QueryRequest 和 QueryResult 架构创建消息变量</span><span class="sxs-lookup"><span data-stu-id="651c7-162">Create Message Variables for QueryRequest and QueryResult Schemas</span></span>  
 <span data-ttu-id="651c7-163">在创建 QueryRequest 和 QueryResult 架构后，你必须在业务流程中创建两个消息变量来表示这两种消息类型。</span><span class="sxs-lookup"><span data-stu-id="651c7-163">After you have created the QueryRequest and QueryResult schemas, you must create two message variables in the orchestration to represent the two message types.</span></span>  
  
#### <a name="to-create-message-variables"></a><span data-ttu-id="651c7-164">创建消息变量</span><span class="sxs-lookup"><span data-stu-id="651c7-164">To create message variables</span></span>  
  
1.  <span data-ttu-id="651c7-165">打开**NotificationService.odx**业务流程和在业务流程视图中，添加两条新消息。</span><span class="sxs-lookup"><span data-stu-id="651c7-165">Open the **NotificationService.odx** orchestration and in the orchestration view, add two new messages.</span></span> <span data-ttu-id="651c7-166">设置为消息名称`QueryRequestMsg`和`QueryResultMsg`。</span><span class="sxs-lookup"><span data-stu-id="651c7-166">Set the message names as `QueryRequestMsg` and `QueryResultMsg`.</span></span>  
  
2.  <span data-ttu-id="651c7-167">设置的消息类型**QueryRequestMsg**作为**BtsSalesforceIntegration.QueryRequest**。</span><span class="sxs-lookup"><span data-stu-id="651c7-167">Set the message type for **QueryRequestMsg** as **BtsSalesforceIntegration.QueryRequest**.</span></span>  
  
3.  <span data-ttu-id="651c7-168">设置的消息类型**QueryResultMsg**作为**BtsSalesforceIntegration.QueryResult**。</span><span class="sxs-lookup"><span data-stu-id="651c7-168">Set the message type for **QueryResultMsg** as **BtsSalesforceIntegration.QueryResult**.</span></span>  
  
4.  <span data-ttu-id="651c7-169">保存对业务流程所做的更改。</span><span class="sxs-lookup"><span data-stu-id="651c7-169">Save changes to the orchestration.</span></span>  
  
## <a name="update-the-orchestration-to-send-message-to-salesforce-and-receive-a-response"></a><span data-ttu-id="651c7-170">更新业务流程以将消息发送到 Salesforce 并接收响应</span><span class="sxs-lookup"><span data-stu-id="651c7-170">Update the Orchestration to Send Message to Salesforce and Receive a Response</span></span>  
 <span data-ttu-id="651c7-171">主题中[步骤 3a： 到 BizTalk Server 中接收 Salesforce 机会通知](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)，我们构建业务流程，接收来自 Salesforce 的机会通知并将发送确认。</span><span class="sxs-lookup"><span data-stu-id="651c7-171">In the topic [Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md), we built the orchestration that receives opportunity notifications from Salesforce and sends an acknowledgement.</span></span> <span data-ttu-id="651c7-172">在此步骤中，我们将在此业务流程的基础上构建，以将查询请求发送到 Salesforce 来获得与机会相关的产品详细信息并接收响应。</span><span class="sxs-lookup"><span data-stu-id="651c7-172">In this step, we build on this orchestration to send a query request to Salesforce to get product details related to the opportunity and receive a response.</span></span> <span data-ttu-id="651c7-173">我们已创建了将在此步骤中使用的架构（QueryRequest.xsd 和 QueryResult.xsd）和消息变量（QueryRequestMsg 和 QueryResultMsg）。</span><span class="sxs-lookup"><span data-stu-id="651c7-173">We have already created the schemas (QueryRequest.xsd and QueryResult.xsd) and the message variables (QueryRequestMsg and QueryResultMsg) that we’ll use in this step.</span></span>  
  
#### <a name="to-send-a-query-request-to-salesforce-and-receive-a-response"></a><span data-ttu-id="651c7-174">向 Salesforce 发送查询请求和接收响应</span><span class="sxs-lookup"><span data-stu-id="651c7-174">To send a query request to Salesforce and receive a response</span></span>  
  
1.  <span data-ttu-id="651c7-175">添加后的构造消息形状**SendNotificationAck**形状。</span><span class="sxs-lookup"><span data-stu-id="651c7-175">Add a Construct Message shape after the **SendNotificationAck** shape.</span></span> <span data-ttu-id="651c7-176">设置到形状的名称`ConstructQuery`并设置**消息构造**属性**QueryRequestMsg**。</span><span class="sxs-lookup"><span data-stu-id="651c7-176">Set the name of the shape to `ConstructQuery` and set the **Messages Constructed** property to **QueryRequestMsg**.</span></span>  
  
2.  <span data-ttu-id="651c7-177">在**ConstructQuery**形状，添加**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="651c7-177">Within the **ConstructQuery** shape, add a **Transform** shape.</span></span> <span data-ttu-id="651c7-178">双击“转换”形状以打开“转换配置”对话框。</span><span class="sxs-lookup"><span data-stu-id="651c7-178">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="651c7-179">在对话框中，选择**现有映射**选项，然后再从下拉列表选中**BtsSalesforceIntegration.Notification_QueryRequest**。</span><span class="sxs-lookup"><span data-stu-id="651c7-179">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.Notification_QueryRequest**.</span></span> <span data-ttu-id="651c7-180">设置**源**到**NotificaitonMessage**，**目标**到**QueryRequestMsg**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="651c7-180">Set **Source** to **NotificaitonMessage**, **Destination** to **QueryRequestMsg**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="651c7-181">在**ConstructQuery**形状之后转换形状中，, 添加消息赋值形状。</span><span class="sxs-lookup"><span data-stu-id="651c7-181">Within the **ConstructQuery** shape, after the Transform shape, add a Message Assignment shape.</span></span> <span data-ttu-id="651c7-182">双击“消息赋值”形状并添加以下表达式：</span><span class="sxs-lookup"><span data-stu-id="651c7-182">Double-click the Message Assignment shape and add the following expression:</span></span>  
  
    ```  
    QueryRequestMsg(BtsSalesforceIntegration.PropertySchema.Query) = QueryRequestMsg.Query;  
    ```  
  
     <span data-ttu-id="651c7-183">通过执行此操作，我们传递的值**查询**中的元素**QueryRequestMsg**到提升的元素的架构**查询**属性架构中。</span><span class="sxs-lookup"><span data-stu-id="651c7-183">By doing this, we pass on the value of the **Query** element in the **QueryRequestMsg** schema to the promoted element **Query** in the property schema.</span></span> <span data-ttu-id="651c7-184">配置 WCF-WebHttp 端口时，我们将使用此元素将查询值动态传递到请求消息。</span><span class="sxs-lookup"><span data-stu-id="651c7-184">While configuring the WCF-WebHttp port, we’ll use this element to dynamically pass on the query value to the request message.</span></span>  
  
4.  <span data-ttu-id="651c7-185">后**ConstructQuery**形状，添加发送形状。</span><span class="sxs-lookup"><span data-stu-id="651c7-185">After the **ConstructQuery** shape, add a Send shape.</span></span> <span data-ttu-id="651c7-186">命名形状`SendQueryRequest`和将消息类型设置为**QueryRequestMsg**。</span><span class="sxs-lookup"><span data-stu-id="651c7-186">Name the shape `SendQueryRequest` and set the message type as **QueryRequestMsg**.</span></span>  
  
5.  <span data-ttu-id="651c7-187">之后发送形状中，添加一个接收形状并将其命名`ReceiveQueryResult`。</span><span class="sxs-lookup"><span data-stu-id="651c7-187">After the Send shape, add a Receive shape and name it `ReceiveQueryResult`.</span></span> <span data-ttu-id="651c7-188">设置到形状的消息类型**QueryResultMsg**。</span><span class="sxs-lookup"><span data-stu-id="651c7-188">Set the message type of the shape to **QueryResultMsg**.</span></span>  
  
6.  <span data-ttu-id="651c7-189">添加端口以向 Salesforce 发送查询请求，并接收作为响应的查询结果。</span><span class="sxs-lookup"><span data-stu-id="651c7-189">Add a port to send query requests to Salesforce and receive the query result in response.</span></span> <span data-ttu-id="651c7-190">在“端口配置”向导中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="651c7-190">In the Port Configuration wizard, select the following options:</span></span>  
  
    -   <span data-ttu-id="651c7-191">将端口名称指定为`SalesforceRESTInterface`。</span><span class="sxs-lookup"><span data-stu-id="651c7-191">Specify the port name as `SalesforceRESTInterface`.</span></span>  
  
    -   <span data-ttu-id="651c7-192">选择用于创建新的端口类型的选项。</span><span class="sxs-lookup"><span data-stu-id="651c7-192">Select the option to create a new port type.</span></span>  
  
    -   <span data-ttu-id="651c7-193">设置**通信模式**到*请求-响应*。</span><span class="sxs-lookup"><span data-stu-id="651c7-193">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
    -   <span data-ttu-id="651c7-194">设置**端口的通信的方向**到*我将发送请求并接收响应*并设置**端口绑定**到*指定更高版本*.</span><span class="sxs-lookup"><span data-stu-id="651c7-194">Set **Port direction of communication** to *I’ll be sending a request and receiving a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="651c7-195">连接**请求**发送形状的端口的操作 (*SendQueryRequest*) 和**响应**接收形状的端口的操作 (*ReceiveQueryResult*)。</span><span class="sxs-lookup"><span data-stu-id="651c7-195">Connect the **Request** operation of port to the Send shape (*SendQueryRequest*) and the **Response** operation of the port to the Receive shape (*ReceiveQueryResult*).</span></span> <span data-ttu-id="651c7-196">下面的屏幕快照描述了业务流程的一部分，它表示向 Salesforce 发送查询请求并接收响应的流程。</span><span class="sxs-lookup"><span data-stu-id="651c7-196">The following screenshot depicts the part of the orchestration that represents the process of sending the query request to Salesforce and receiving a response.</span></span>  
  
     <span data-ttu-id="651c7-197">![将查询发送到 Salesforce 和接收响应](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span><span class="sxs-lookup"><span data-stu-id="651c7-197">![Send a query to Salesforce and receive response](../core/media/bts-sf-sendqueryrequestorch.jpg "BTS_SF_SendQueryRequestOrch")</span></span>  
  
 <span data-ttu-id="651c7-198">在本主题中，我们更新了业务流程以向 Salesforce 发送查询请求，并接收与 Salesforce 中创建的机会有关的详细信息（如产品、数量等）。</span><span class="sxs-lookup"><span data-stu-id="651c7-198">In this topic, we updated the orchestration to send a query request to Salesforce and receive more details (such as products, quantity, etc.) about the opportunity that is created in Salesforce.</span></span> <span data-ttu-id="651c7-199">在随后的主题中，我们将更新此解决方案，以将 Salesforce 响应输入到本地的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="651c7-199">In the subsequent topics, we will update this solution to enter the Salesforce response into an on-premise SQL Server database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651c7-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="651c7-200">See Also</span></span>  
 [<span data-ttu-id="651c7-201">步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案</span><span class="sxs-lookup"><span data-stu-id="651c7-201">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)