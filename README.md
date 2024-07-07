# ML
This code is used for machine learning to build predictive models, variable importance analysis and 1:1 line output of measured and predicted values (RF\BRT\XGBOOST)
The main steps are as follows:
A.  The original data is randomly divided into a training set and a test set according to 7:3. The training set is used to build the machine learning model, and the verification set is used to evaluate the generalization ability of the model.
B.  Based on training set data, find the most suitable parameters of the machine learning model, RF including mtry and ntree, BRT including n.rees, interaction.depth, shrinkage and n.shrinkage node, XGBoost includes nrounds, nrounds, eta, gamma, colsample_bytree, min_child_weight, and subsample.
C.  定义一个函数，函数的输入参数是不同的种子数，函数的主体是基于B步骤里寻找到的最佳参数使用输入的种子数循环建立多个机器学习模型，并对建立的机器学习模型进行精度参数的输出。例如，输入100个不同的种子数，将建立100次模型，取100次模型的精度评价指标的平均值作为模型的评价结果，输出精度指标。这样可以避免模型不受随机种子数的影响。
D.  种子数保持一致，再次执行C步骤建立的100个模型，使用predict函数，输入数据为测试集数据，计算模型
输出每个模型中各个变量的相对重要性，将各个变量的相对重要性进行加和再归一化得到各个变量的相对重要性。
E.  种子数保持一致，再次执行C步骤建立的100个模型，输出每个模型中各个变量的相对重要性，将各个变量的相对重要性进行加和再归一化得到各个变量的相对重要性。
