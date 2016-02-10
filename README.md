# 1
3d Sphere with three.js
//will create a sphere 
			var scene = new THREE.Scene();
			var camera = new THREE.PerspectiveCamera( 75, window.innerWidth/window.innerHeight, 0.1, 1000 );

			var renderer = new THREE.WebGLRenderer( {alpha:true });
			renderer.setClearColor( 0xffffff, 0 );
			renderer.setSize( window.innerWidth, window.innerHeight );
			document.body.appendChild( renderer.domElement );

			camera.position.z = 5;

			var spheregeometry = new THREE.SphereGeometry(2.2, 36, 36).rotateX(180);
            var spherematerial = new THREE.MeshBasicMaterial({wireframe: true, color: 0x000000});
            var sphere = new THREE.Mesh(spheregeometry, spherematerial);
 
            sphere.position.set(0, 0, 0);
 
            scene.add(sphere);

			var render = function () {
				requestAnimationFrame( render );

				 sphere.rotation.y += 0.02;

				renderer.render(scene, camera);
			};

			render();
			
