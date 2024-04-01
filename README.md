# mongodb_task

	-use Guvi;
		-db.createCollection ('users');
		-db.users.insertMany ([{}]);
  
		1 -db.users.find({});
			
		2 -db.users.find({$and:[{product_price:{$gt:400}},{product_price:{$lt:800}}]},{});
  
  		3-db.users.find({product_price:{$not:{$gt:400,$lt:600}}});
   
   		4 -db.users.find({product_price:{$gt:500}}

   		5 -db.users.find({},{_id:0,product_name:1,product_material:1});
     
  		6 -db.users.find({id:{$eq:'10'}},{_id:0});).limit(4);
   
   		7 -db.users.find({},{_id:0,product_name:1,product_material:1});
   
   		8 -db.users.find({product_material:{$eq:'Soft'}},{});
   
   		9 -db.users.find({$or:[{product_color:'indigo'},{product_price:492}]});
     
     		10 -db.users.aggregate([{$group:{_id:{product_price:'$product_price'},total:{$sum:1}}},
		    {$match:{total:{$gt:1}}}]).map(val=> db.users.deleteMany({'product_price':val._id.product_price}));
