export default function AryaFarmStore() { const products = [ { id: 1, name: "Arya Organic Desi Wheat", price: 2000, unit: "55 kg", description: "Premium Organic + Desi Variety Wheat. 100% Chemical Free. Limited Farm Stock. Direct From Nashik Farmer.", image: "/wheat.jpg" }, ];

const whatsappNumber = "917620570910";

const handleOrder = (product) => { const message = Hello, I want to order ${product.name} - ${product.unit} for ₹${product.price}; const url = https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}; window.open(url, "_blank"); };

return ( <div className="min-h-screen bg-gray-50 p-6"> <div className="max-w-4xl mx-auto"> <h1 className="text-3xl font-bold text-center mb-2">Arya Farm Premium Store</h1> <p className="text-center text-gray-600 mb-8"> Organic • Desi Variety • Chemical Free • Limited Stock </p>

<div className="grid md:grid-cols-2 gap-6">
      {products.map((product) => (
        <div
          key={product.id}
          className="bg-white rounded-2xl shadow-md p-6 flex flex-col justify-between"
        >
          <div>
            <img
              src={product.image}
              alt={product.name}
              className="rounded-xl mb-4 w-full h-64 object-cover"
            />
            <h2 className="text-xl font-semibold mb-2">{product.name}</h2>
            <p className="text-gray-600 mb-2">{product.description}</p>
            <p className="text-lg font-bold mb-2">₹{product.price} / {product.unit}</p>
            <p className="text-sm text-gray-500 mb-4">
              Delivery: Nashik District | Payment: UPI (7620570910)
            </p>
          </div>
          <button
            onClick={() => handleOrder(product)}
            className="bg-green-600 text-white py-2 px-4 rounded-xl hover:bg-green-700 transition"
          >
            Order on WhatsApp
          </button>
        </div>
      ))}
    </div>

    <div className="mt-12 bg-white rounded-2xl shadow-md p-6">
      <h2 className="text-xl font-semibold mb-2">Farm Location</h2>
      <p className="text-gray-700">
        Konambe Village, Sinnar Sub-District,<br />
        Nashik District, Maharashtra, India
      </p>
      <p className="text-sm text-gray-500 mt-2">
        Direct pickup available from farm (prior WhatsApp confirmation required).
      </p>
    </div>

  </div>
</div>

); }
