# 04-STORE-API
getting errors:

<code>
  require('dotenv').config()

const connectDB = require('./db/connect')
const Product = require('./models/product')

const jsonProducts = require('./products.json')

const start = async () => {
  try {
    await connectDB(process.env.MONGO_URI)
    await Product.deleteMany()
    await Product.create(jsonProducts)
    console.log('Success!!!!')
    process.exit(0)
  } catch (error) {
    console.log(error)
    process.exit(1)
  }
}

start()

  <code>
TypeError: Product.deleteMany is not a function
    at start (/Users/keex/Desktop/node-express-course-main/04-store-api/starter/populate.js:11:19)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
