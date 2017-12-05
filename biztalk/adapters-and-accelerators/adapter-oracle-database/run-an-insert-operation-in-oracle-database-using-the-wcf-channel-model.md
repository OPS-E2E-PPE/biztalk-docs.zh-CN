---
title: "使用 WCF 通道模型的 Oracle 数据库中运行插入操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inserting data, using a channel
- WCF channel model, performing an Insert operation
- how to, perform an insert operation using a channel
- channel programming, performing an insert operation
- performing an insert operation, using a channel
ms.assetid: 85c44507-0166-42ef-a908-6098f7a683fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fd689cbf378f41578c5f46b3067410a184cf650
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="b432c-102">使用 WCF 通道模型的 Oracle 数据库中运行插入操作</span><span class="sxs-lookup"><span data-stu-id="b432c-102">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="b432c-103">本部分演示如何将一个记录插入 Oracle 数据库通过通道进行。</span><span class="sxs-lookup"><span data-stu-id="b432c-103">This section shows how to insert a record into an Oracle database by using a channel.</span></span> <span data-ttu-id="b432c-104">当你发送一条消息时，必须指定消息正文和消息操作。</span><span class="sxs-lookup"><span data-stu-id="b432c-104">You must specify both a message body and a message action when you send a message.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="b432c-105">插入消息</span><span class="sxs-lookup"><span data-stu-id="b432c-105">The Insert Message</span></span>  
 <span data-ttu-id="b432c-106">下面的 XML 演示在 HR 插入操作的消息正文。员工表。</span><span class="sxs-lookup"><span data-stu-id="b432c-106">The following XML shows a message body for an Insert operation on the HR.EMPLOYEES table.</span></span> <span data-ttu-id="b432c-107">记录集包含单个员工记录。</span><span class="sxs-lookup"><span data-stu-id="b432c-107">The record set consists of a single employee record.</span></span> <span data-ttu-id="b432c-108">Insert 消息架构的详细信息，请参阅[基本插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="b432c-108">For more information about the schema of an Insert message, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span> <span data-ttu-id="b432c-109">这是示例中使用 Employee_Insert.xml 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="b432c-109">This is the contents of the Employee_Insert.xml file used in the example.</span></span>  
  
```  
<!-- New namespace: http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES -->  
<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES">  
    <RECORDSET xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
        <EMPLOYEESRECORDINSERT>  
            <EMPLOYEE_ID>0</EMPLOYEE_ID>  
            <FIRST_NAME>Anton</FIRST_NAME>  
            <LAST_NAME>Kirilov</LAST_NAME>  
            <EMAIL></EMAIL>  
            <PHONE_NUMBER>555-0198</PHONE_NUMBER>  
            <HIRE_DATE>2007-03-01T00:00:00.0000000</HIRE_DATE>  
            <JOB_ID>FI_ACCOUNT</JOB_ID>  
            <SALARY>5000</SALARY>  
            <COMMISSION_PCT>0.15</COMMISSION_PCT>  
            <MANAGER_ID>108</MANAGER_ID>  
            <DEPARTMENT_ID>100</DEPARTMENT_ID>  
       </EMPLOYEESRECORDINSERT>  
    </RECORDSET>  
</Insert>  
```  
  
## <a name="specifying-the-message-action"></a><span data-ttu-id="b432c-110">指定的消息操作</span><span class="sxs-lookup"><span data-stu-id="b432c-110">Specifying the Message Action</span></span>  
 <span data-ttu-id="b432c-111">当你发送到的 SOAP 消息时，必须指定消息操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b432c-111">You must specify a message action when you send a SOAP message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="b432c-112">在创建如以下示例所示的消息时，你可以指定的消息操作。</span><span class="sxs-lookup"><span data-stu-id="b432c-112">You can specify the message action when you create the message as in the following example.</span></span>  
  
```  
Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert", readerIn2);  
```  
  
 <span data-ttu-id="b432c-113">消息操作在此示例中，"/ HR/表/员工/插入"，指定对 HR 的插入操作。EMPLOYEES 表是执行</span><span class="sxs-lookup"><span data-stu-id="b432c-113">The message action in this example, "/HR/Table/EMPLOYEES/Insert", specifies that an Insert operation on the HR.EMPLOYEES table is to be performed</span></span>  
  
## <a name="sending-the-insert-message"></a><span data-ttu-id="b432c-114">发送的 Insert 消息</span><span class="sxs-lookup"><span data-stu-id="b432c-114">Sending the Insert Message</span></span>  
 <span data-ttu-id="b432c-115">此示例演示如何通过通道执行对 Oracle 表的插入操作。</span><span class="sxs-lookup"><span data-stu-id="b432c-115">This example shows how to perform an Insert operation on an Oracle table over a channel.</span></span> <span data-ttu-id="b432c-116">该代码使用公开 SQLEXECUTE 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]返回 Oracle 序列的下一个值。</span><span class="sxs-lookup"><span data-stu-id="b432c-116">The code uses the SQLEXECUTE operation exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to return the next value of an Oracle SEQUENCE.</span></span> <span data-ttu-id="b432c-117">此值然后写入中插入记录的 EMPLOYEE_ID 字段。</span><span class="sxs-lookup"><span data-stu-id="b432c-117">This value is then written to the EMPLOYEE_ID field in the Insert record.</span></span> <span data-ttu-id="b432c-118">此模式，可将行插入到具有自动生成主键值的数据库。</span><span class="sxs-lookup"><span data-stu-id="b432c-118">This pattern enables you to insert rows into databases that have an auto-generated primary key value.</span></span> <span data-ttu-id="b432c-119">有关通过通道调用 SQLEXECUTE 操作的详细信息，请参阅[使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="b432c-119">For more information about invoking the SQLEXECUTE operation over a channel, see [Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
using Microsoft.ServiceModel.Adapters;  
using Microsoft.Adapters.OracleDB;  
  
namespace OracleDMLChannel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create Endpoint  
            EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
            // Create Binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            // Create Channel Factory  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
            factory.Credentials.UserName.UserName = "HR";  
            factory.Credentials.UserName.Password = "TIGER";  
            factory.Open();  
  
            // Create Request Channel  
            IRequestChannel channel = factory.CreateChannel();  
            channel.Open();  
  
            // Send Request  
            System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
            Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
            Message messageOut = channel.Request(messageIn);  
  
            // Get Response XML  
            XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
            // Get Employee ID  
            string id = null;  
            XmlDocument doc = new XmlDocument();  
            doc.Load(readerOut);  
            XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
            if (list.Count > 0) id = list[0].InnerXml;  
  
            // Compose Insert XML  
            XmlDocument insertDoc = new XmlDocument();  
            insertDoc.Load("Employee_Insert.xml");  
  
            // Change Employee ID  
            XmlNodeList empidList = insertDoc.GetElementsByTagName("EMPLOYEE_ID");  
            XmlNode empidNode = empidList[0];  
            empidNode.InnerXml = id;  
  
            // Change email  
            XmlNodeList emailList = insertDoc.GetElementsByTagName("EMAIL");  
            XmlNode emailNode = emailList[0];  
            emailNode.InnerXml = "scotty" + id + "@microsoft.com";  
  
            // Change date  
            XmlNodeList dateList = insertDoc.GetElementsByTagName("HIRE_DATE");  
            XmlNode dateNode = dateList[0];  
            dateNode.InnerXml = "2007-03-01T00:00:00.0000000";  
  
            StringReader strReader = new StringReader(insertDoc.InnerXml);  
            XmlReader readerIn2 = XmlReader.Create(strReader);  
  
            // Send XML  
            Message messageIn2 = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEES/Insert ", readerIn2);  
            Message messageOut2 = channel.Request(messageIn2);  
  
            // Close the messages  
            messageOut.Close();  
            messageOut2.Close();  
  
            channel.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b432c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b432c-120">See Also</span></span>  
 <span data-ttu-id="b432c-121">[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="b432c-121">[Develop Oracle Database applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) </span></span>  
 <span data-ttu-id="b432c-122">[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="b432c-122">[Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) </span></span>  
 <span data-ttu-id="b432c-123">[使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span><span class="sxs-lookup"><span data-stu-id="b432c-123">[Run a SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md) </span></span>  
 [<span data-ttu-id="b432c-124">调用中使用 WCF 通道模型的 Oracle 数据库的函数</span><span class="sxs-lookup"><span data-stu-id="b432c-124">Invoke a Function in Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)