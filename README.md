# React_Learning_02

eComm

=> (npx create-react-app frontend)

=> Clean folder

=> Change App.js to arrowFunction

=> Make git to root folder (rm -rf .git)

- move (.gitignore) to root folder
- edit (.gitignore) (node_modules
  node_modules/) + (.env)

=> Create in (src) folder (components) folder && (Header.js && Footer.js)

=> In (App.js) create (main) tag && (<Header /> & <Footer />) on top and bot

=> Bring from bootswatch.com -> Theme (bootstrap.min.css) to (src) folder &&

- import it to (index.js) (import './bootstrap.min.css')
- install react-bootstrap in frontend folder (npm i react-bootstrap)

=> (import { Container } from 'react-bootstrap') to (App.js)

- && wrap (<h1>) with (<Container>)

=> In Footer.js component

- (import { Container, Row, Col } from 'react-bootstrap')
- (<footer> -> <Container> -> <Row> -> <Col className='text-center py-3'>Copyright &copy; ProShop</Col>)

=> In (index.css) write (main { min-height: 80vh })

=> Bring Navbar layout from react-bootstrap.io to (Header.js)

- chg (<Nav.Link>) root tag (className='ms-auto')
- chg (<Navbar bg='dark' variant='dark' expand='lg' collapseOnSelect>)

=> Wrap below (<Navbar>) -> (<Container>)

=> Bring Link fontAwesome for icons (<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" referrerpolicy="no-referrer" />)

- Bring icons to (<Nav.Link>)(<i className='fas fa-shopping-cart'></i>)

=> Bring folder (images) to (public) folder

=> Bring (product.js) to (src) folder

=> Create (screens) folder in (src) folder

- Create (HomeScreen.js) in (screens) folder

=> In (HomeScreen.js)

- (import products from '../products')
- Bring (
<Row>
{products.map((product) => (
 <Col sm={12} md={6} lg={4} xl={3}>
 <Product product={product} />
 </Col>
 ))}
 </Row> )

=> Create ( Product.js ) in components

- (
  import React from 'react';
  import { Card } from 'react-bootstrap';

const Product = ({ product }) => {
return (
<Card className='my-3 p-3 rounded'>
<a href={`/product/${product._id}`}>
<Card.Img src={product.image} variant='top' />
</a>

<Card.Body>
<a href={`/product/${product._id}`}>
<Card.Title as='div'>
<strong>{product.name}</strong>
</Card.Title>
</a>

    <Card.Text as='div'>
     <div className='my-3'>
      {product.rating} from {product.numReviews} reviews
     </div>
    </Card.Text>

    <Card.Text as='h3'>${product.price}</Card.Text>

</Card.Body>
</Card>
);
};

export default Product;
)

=> Routing (i in frontend)
{ npm i react-router-dom react-router-bootstrap}

- Wrap in (App.js) root tag with ( <Router> ) &&
- Componentd like this ( <Route path='/' component={HomeScreen} exact /> )

=> ( import { Link } from 'react-router-dom'; ) to ( Product.js ) &&

- Change a tag to Link tag
- # Change href to to

  => import { LinkContainer } from 'react-router-bootstrap'; to ( Header.js ) &&

  - Wrap tags with href like this:
    <LinkContainer to='/'>
    <Navbar.Brand>ProShop</Navbar.Brand>
    </LinkContainer>
