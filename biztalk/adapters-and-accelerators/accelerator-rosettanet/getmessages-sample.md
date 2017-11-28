---
title: "GetMessages 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ebc4ce5b87a0b698f0295fdf29c8f7138efed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getmessages-sample"></a><span data-ttu-id="5b89b-102">GetMessages 示例</span><span class="sxs-lookup"><span data-stu-id="5b89b-102">GetMessages Sample</span></span>
<span data-ttu-id="5b89b-103">本主题提供的示例代码可以用于从一个消息不可否认性表或一个业务线 (LOB) 表中检索可读格式的消息。</span><span class="sxs-lookup"><span data-stu-id="5b89b-103">This topic provides sample code that you can use to retrieve messages from one of the message non-repudiation tables or one of the line-of-business (LOB) tables in a readable form.</span></span> <span data-ttu-id="5b89b-104">消息不可否认性表包括 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive 数据库中的 MessageStorageIn 和 MessageStorageOut；LOB 表包括 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA 数据库中的 MessageFromLOB 和 MessageToLOB。</span><span class="sxs-lookup"><span data-stu-id="5b89b-104">The message non-repudiation tables include MessageStorageIn and MessageStorageOut in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive database; the LOB tables include MessageFromLOB and MessageToLOB in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span>  
  
 <span data-ttu-id="5b89b-105">将 `GetMessages` 用于故障排除或开发。</span><span class="sxs-lookup"><span data-stu-id="5b89b-105">Use `GetMessages` for either troubleshooting or development.</span></span> <span data-ttu-id="5b89b-106">默认情况下，代码返回一个 base 64 字符串。</span><span class="sxs-lookup"><span data-stu-id="5b89b-106">By default, the code returns a base 64 string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b89b-107">GetMessages.cs 示例代码包含两段代码，一段用于从  LOB 表中检索消息，另一段用于从不可否认性表中检索消息。</span><span class="sxs-lookup"><span data-stu-id="5b89b-107">The GetMessages.cs sample code contains two sections of code—one for retrieving messages from one of the LOB tables, and one for retrieving messages from one of the non-repudiation tables.</span></span> <span data-ttu-id="5b89b-108">请为每种用途创建单独的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b89b-108">Create separate applications for each purpose.</span></span>  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a><span data-ttu-id="5b89b-109">从 LOB 表中检索消息</span><span class="sxs-lookup"><span data-stu-id="5b89b-109">To retrieve messages from an LOB table</span></span>  
  
1.  <span data-ttu-id="5b89b-110">向您的程序中添加以下示例代码：</span><span class="sxs-lookup"><span data-stu-id="5b89b-110">Add the following sample code to your program:</span></span>  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="5b89b-111">将 `sMessageSource` 参数设置为 MessagesFromLOB 或 MessagesToLOB 表。</span><span class="sxs-lookup"><span data-stu-id="5b89b-111">Set the `sMessageSource` parameter to either the MessagesFromLOB or MessagesToLOB table.</span></span>  
  
3.  <span data-ttu-id="5b89b-112">设置`sMessageID`参数的值**MessageID**数据库中的字段。</span><span class="sxs-lookup"><span data-stu-id="5b89b-112">Set the `sMessageID` parameter to the value of the **MessageID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b89b-113">应用程序将返回包含所检索的消息的字符串。</span><span class="sxs-lookup"><span data-stu-id="5b89b-113">The application returns a string that contains the retrieved message.</span></span>  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a><span data-ttu-id="5b89b-114">从不可否认性表中检索消息</span><span class="sxs-lookup"><span data-stu-id="5b89b-114">To retrieve messages from a non-repudiation table</span></span>  
  
1.  <span data-ttu-id="5b89b-115">向您的程序中添加以下示例代码：</span><span class="sxs-lookup"><span data-stu-id="5b89b-115">Add the following sample code to your program:</span></span>  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="5b89b-116">将 `sMessageSource` 参数设置为 MessageStorageIn 或 MessageStorageOut 表。</span><span class="sxs-lookup"><span data-stu-id="5b89b-116">Set the `sMessageSource` parameter to either the MessageStorageIn or MessageStorageOut table.</span></span>  
  
3.  <span data-ttu-id="5b89b-117">设置`sMessageID`参数的值**RecordID**数据库中的字段。</span><span class="sxs-lookup"><span data-stu-id="5b89b-117">Set the `sMessageID` parameter to the value of the **RecordID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b89b-118">应用程序将返回包含所检索的消息的字符串。</span><span class="sxs-lookup"><span data-stu-id="5b89b-118">The application returns a string that contains the retrieved message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5b89b-119">演示</span><span class="sxs-lookup"><span data-stu-id="5b89b-119">Demonstrates</span></span>  
 <span data-ttu-id="5b89b-120">GetMessages 示例包括以下两部分代码：</span><span class="sxs-lookup"><span data-stu-id="5b89b-120">The GetMessages sample includes the following two sections of code:</span></span>  
  
-   <span data-ttu-id="5b89b-121">一部分代码向您展示如何从一个不可否认性表中检索二进制格式的消息，并将其转换为可读的 ASCII 格式。</span><span class="sxs-lookup"><span data-stu-id="5b89b-121">One section shows you how to retrieve a binary message from one of the non-repudiation tables, and convert it into readable ASCII form.</span></span>  
  
-   <span data-ttu-id="5b89b-122">另一部分代码向您展示如何从一个 LOB 表中检索消息。</span><span class="sxs-lookup"><span data-stu-id="5b89b-122">The other section shows you how to retrieve a message from one of the LOB tables.</span></span> <span data-ttu-id="5b89b-123">由于 LOB 表中的消息已经是 ASCII 格式，因此这是一个 SQL select 语句。</span><span class="sxs-lookup"><span data-stu-id="5b89b-123">Because a message in an LOB table is already in ASCII form, this is a SQL select statement.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5b89b-124">出于演示目的，所提供的示例代码直接使用了 SQL 语句，而这可能会导致 SQL 注入漏洞。</span><span class="sxs-lookup"><span data-stu-id="5b89b-124">For demonstration purposes, the sample code provided uses a direct SQL statement that is prone to SQL injection vulnerabilities.</span></span> <span data-ttu-id="5b89b-125">在生产环境下，建议使用参数化的 SQL 存储过程，而不要直接使用 SQL 语句，以防止出现这种漏洞。</span><span class="sxs-lookup"><span data-stu-id="5b89b-125">In a production environment, it is recommended that you use parameterized SQL stored procedures, instead of the direct SQL statement, to prevent such vulnerabilities.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b89b-126">示例</span><span class="sxs-lookup"><span data-stu-id="5b89b-126">Example</span></span>  
 <span data-ttu-id="5b89b-127">使用以下代码示例两部分中的任何一部分，从一个不可否认性表或一个 LOB 表中检索消息。</span><span class="sxs-lookup"><span data-stu-id="5b89b-127">Use one of the two sections in the following code example for retrieving messages from one of the non-repudiation tables or one of the LOB tables.</span></span>  
  
```  
using System;  
using System.Text;  
using System.Data.SqlClient;   
using Microsoft.Solutions.BTARN.Shared;  
  
namespace Microsoft.Solutions.BTARN.Admin  
{  
  
      /// <summary>  
      /// Summary description for GetMessages.  
      /// </summary>  
      class GetMessages  
      {  
            /// <summary>  
            /// The main entry point for the application.  
            /// </summary>  
            [STAThread]  
            static void Main(string[] args)  
            {  
                  Console.WriteLine(GetLOBMessage("MessagesFromLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetLOBMessage("MessagesToLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetNRMessage("MessageStorageIn", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
                  Console.WriteLine(GetNRMessage("MessageStorageOut", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
            }  
  
            /// <summary>  
            /// Retrieve a message from the LOB tables in the BTARNDATA database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessagesFromLOB or MessagesToLOB</param>  
            /// <param name="sMessageID">The value of the MessageID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>        
            private static string GetLOBMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.DataDbConnectionString);  
                  sQuery = "SELECT ServiceContent from " + sMessageSource + " WHERE MessageID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                        sReturnedMessage=localReader.GetString(0);  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
  
            /// <summary>  
            /// Retrieve a message from the non-repudiation tables in the BTARNArchive database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessageStorageIn or MessageStorageOut</param>  
            /// <param name="sMessageID">The value of the RecordID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>  
            private static string GetNRMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.ArchiveDbConnectionString);  
                  sQuery = "SELECT Content from " + sMessageSource + " WHERE RecordID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                  {  
                        //Determine the size of the field in bytes and create a new byte array  
                        byte[] bData= new byte[localReader.GetBytes(0, 0, null, 0, 0)];  
  
                        //Read the value of the field into bData  
                        localReader.GetBytes(0, 0, bData, 0, bData.Length);  
  
                        //Convert the byte array into a string  
                        sReturnedMessage=Encoding.ASCII.GetString(bData);  
                  }  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
      }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b89b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b89b-128">See Also</span></span>  
 [<span data-ttu-id="5b89b-129">消息传送示例</span><span class="sxs-lookup"><span data-stu-id="5b89b-129">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)