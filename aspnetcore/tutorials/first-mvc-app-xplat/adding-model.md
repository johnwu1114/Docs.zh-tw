---
title: "新增模型"
author: rick-anderson
description: "請將模型新增至簡單的 ASP.NET Core 應用程式。"
keywords: ASP.NET Core,
ms.author: riande
manager: wpickett
ms.date: 03/30/2017
ms.topic: get-started-article
ms.assetid: 8dc28498-eeee-4666-b903-b593059e9f39
ms.technology: aspnet
ms.prod: asp.net-core
uid: tutorials/first-mvc-app-xplat/adding-model
ms.openlocfilehash: c68466a645687b6fe0193e9deec2f32632e6f0e7
ms.sourcegitcommit: 9cdbfd0d670d70b9c354216aabee260c52dad5ee
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2017
---
[!INCLUDE[adding-model1](../../includes/mvc-intro/adding-model1.md)]

* <span data-ttu-id="018b3-104">將類別新增至名為 *Movie.cs* 的 *Models* 資料夾。</span><span class="sxs-lookup"><span data-stu-id="018b3-104">Add a class to the *Models* folder named *Movie.cs*.</span></span>
* <span data-ttu-id="018b3-105">將下列程式碼新增至 *Models/Movie.cs* 檔案：</span><span class="sxs-lookup"><span data-stu-id="018b3-105">Add the following code to the *Models/Movie.cs* file:</span></span>

<span data-ttu-id="018b3-106">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Models/MovieNoEF.cs?name=snippet_1)]</span><span class="sxs-lookup"><span data-stu-id="018b3-106">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Models/MovieNoEF.cs?name=snippet_1)]</span></span>

<span data-ttu-id="018b3-107">`ID` 欄位是資料庫對於主索引鍵的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="018b3-107">The `ID` field is required by the database for the primary key.</span></span> 

<span data-ttu-id="018b3-108">建置應用程式，以確認您沒有任何錯誤，而且您最後已將**模型**新增至 **MVC** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="018b3-108">Build the app to verify you don't have any errors, and you've finally added a **M**odel to your **M**VC app.</span></span>

## <a name="prepare-the-project-for-scaffolding"></a><span data-ttu-id="018b3-109">準備專案進行 Scaffolding</span><span class="sxs-lookup"><span data-stu-id="018b3-109">Prepare the project for scaffolding</span></span>

- <span data-ttu-id="018b3-110">將下列反白顯示的 NuGet 套件新增至 *MvcMovie.csproj* 檔案：</span><span class="sxs-lookup"><span data-stu-id="018b3-110">Add the following highlighted NuGet packages to the *MvcMovie.csproj* file:</span></span>
             
   <span data-ttu-id="018b3-111">[!code-csharp[Main](start-mvc/sample/MvcMovie/MvcMovie.csproj?highlight=7,10)]</span><span class="sxs-lookup"><span data-stu-id="018b3-111">[!code-csharp[Main](start-mvc/sample/MvcMovie/MvcMovie.csproj?highlight=7,10)]</span></span>

- <span data-ttu-id="018b3-112">選取檔案，然後選取 [還原] 至 [資訊] 訊息「有未解析的相依性」。</span><span class="sxs-lookup"><span data-stu-id="018b3-112">Save the file and select **Restore** to the **Info** message "There are unresolved dependencies".</span></span>
- <span data-ttu-id="018b3-113">建立 *Models/MvcMovieContext.cs* 檔案，然後新增下列 `MvcMovieContext` 類別：</span><span class="sxs-lookup"><span data-stu-id="018b3-113">Create a *Models/MvcMovieContext.cs* file and add the following `MvcMovieContext` class:</span></span>

   <span data-ttu-id="018b3-114">[!code-csharp[Main](start-mvc/sample/MvcMovie/Models/MvcMovieContext.cs)]</span><span class="sxs-lookup"><span data-stu-id="018b3-114">[!code-csharp[Main](start-mvc/sample/MvcMovie/Models/MvcMovieContext.cs)]</span></span>
   
- <span data-ttu-id="018b3-115">開啟 *Startup.cs* 檔案，然後新增兩個 using：</span><span class="sxs-lookup"><span data-stu-id="018b3-115">Open the *Startup.cs* file and add two usings:</span></span>

   <span data-ttu-id="018b3-116">[!code-csharp[Main](start-mvc/sample/MvcMovie/Startup.cs?name=snippet1&highlight=1,2)]</span><span class="sxs-lookup"><span data-stu-id="018b3-116">[!code-csharp[Main](start-mvc/sample/MvcMovie/Startup.cs?name=snippet1&highlight=1,2)]</span></span>

- <span data-ttu-id="018b3-117">將資料庫內容新增至 *Startup.cs* 檔案：</span><span class="sxs-lookup"><span data-stu-id="018b3-117">Add the database context to the *Startup.cs* file:</span></span>

   <span data-ttu-id="018b3-118">[!code-csharp[Main](start-mvc/sample/MvcMovie/Startup.cs?name=snippet2&highlight=6-7)]</span><span class="sxs-lookup"><span data-stu-id="018b3-118">[!code-csharp[Main](start-mvc/sample/MvcMovie/Startup.cs?name=snippet2&highlight=6-7)]</span></span>

  <span data-ttu-id="018b3-119">這會告知 Entity Framework 哪些模型類別包含在資料模型中。</span><span class="sxs-lookup"><span data-stu-id="018b3-119">This tells Entity Framework which model classes are included in the data model.</span></span> <span data-ttu-id="018b3-120">您是在定義電影物件的一個「實體集」，它會在資料庫中以「電影」資料表表示。</span><span class="sxs-lookup"><span data-stu-id="018b3-120">You're defining one *entity set* of Movie objects, which will be represented in the database as a Movie table.</span></span>

- <span data-ttu-id="018b3-121">建置專案以確認沒有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="018b3-121">Build the project to verify there are no errors.</span></span>

## <a name="scaffold-the-moviecontroller"></a><span data-ttu-id="018b3-122">Scaffold MovieController</span><span class="sxs-lookup"><span data-stu-id="018b3-122">Scaffold the MovieController</span></span>

<span data-ttu-id="018b3-123">在專案資料夾中開啟終端機視窗，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="018b3-123">Open a terminal window in the project folder and run the following commands:</span></span>

```
dotnet restore
dotnet aspnet-codegenerator controller -name MoviesController -m Movie -dc MvcMovieContext --relativeFolderPath Controllers --useDefaultLayout --referenceScriptLibraries 
```

> [!NOTE]
> <span data-ttu-id="018b3-124">如果您在 Scaffolding 命令執行時收到錯誤，請參閱 [Scaffolding 儲存機制中的問題 444](https://github.com/aspnet/scaffolding/issues/444) 以了解因應措施。</span><span class="sxs-lookup"><span data-stu-id="018b3-124">If you get an error when the scaffolding command runs, see [issue 444 in the scaffolding repository](https://github.com/aspnet/scaffolding/issues/444) for a workaround.</span></span>

<span data-ttu-id="018b3-125">Scaffolding 引擎會建立下列各項：</span><span class="sxs-lookup"><span data-stu-id="018b3-125">The scaffolding engine creates the following:</span></span>

* <span data-ttu-id="018b3-126">電影控制器 (*Controllers/MoviesController.cs*)</span><span class="sxs-lookup"><span data-stu-id="018b3-126">A movies controller (*Controllers/MoviesController.cs*)</span></span>
* <span data-ttu-id="018b3-127">Create、Delete、Details、Edit 和 Index 頁面的 Razor 檢視檔案 (*Views/Movies/\*.cshtml*)</span><span class="sxs-lookup"><span data-stu-id="018b3-127">Razor view files for Create, Delete, Details, Edit and Index pages (*Views/Movies/\*.cshtml*)</span></span>

<span data-ttu-id="018b3-128">自動建立 [CRUD](https://wikipedia.org/wiki/Create,_read,_update_and_delete) (建立、讀取、更新和刪除) 動作方法和檢視稱為 *Scaffolding*。</span><span class="sxs-lookup"><span data-stu-id="018b3-128">The automatic creation of [CRUD](https://wikipedia.org/wiki/Create,_read,_update_and_delete) (create, read, update, and delete) action methods and views is known as *scaffolding*.</span></span> <span data-ttu-id="018b3-129">您很快就會擁有一個正常運作的 Web 應用程式，可讓您管理電影資料庫。</span><span class="sxs-lookup"><span data-stu-id="018b3-129">You'll soon have a fully functional web application that lets you manage a movie database.</span></span>

[!INCLUDE[adding-model 2x](../../includes/mvc-intro/adding-model2xp.md)]

[!INCLUDE[adding-model](../../includes/mvc-intro/adding-model3.md)]

<span data-ttu-id="018b3-130">您現在擁有一個資料庫和多個頁面，可用來顯示、編輯、更新和刪除資料。</span><span class="sxs-lookup"><span data-stu-id="018b3-130">You now have a database and pages to display, edit, update and delete data.</span></span> <span data-ttu-id="018b3-131">在下一個教學課程中，我們將會使用資料庫。</span><span class="sxs-lookup"><span data-stu-id="018b3-131">In the next tutorial, we'll work with the database.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="018b3-132">其他資源</span><span class="sxs-lookup"><span data-stu-id="018b3-132">Additional resources</span></span>

* [<span data-ttu-id="018b3-133">標記協助程式</span><span class="sxs-lookup"><span data-stu-id="018b3-133">Tag Helpers</span></span>](xref:mvc/views/tag-helpers/intro)
* [<span data-ttu-id="018b3-134">全球化和當地語系化</span><span class="sxs-lookup"><span data-stu-id="018b3-134">Globalization and localization</span></span>](xref:fundamentals/localization)

>[!div class="step-by-step"]
<span data-ttu-id="018b3-135">[上一步 - 新增檢視](adding-view.md)
[下一步 - 使用 SQLite](working-with-sql.md)</span><span class="sxs-lookup"><span data-stu-id="018b3-135">[Previous - Add a view](adding-view.md)
[Next - Working with SQLite](working-with-sql.md)</span></span>